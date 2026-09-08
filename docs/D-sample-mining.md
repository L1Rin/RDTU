[Home](../README.md) · [Reading guide](index.md) · [Complete PDF](../supplement/RDTU-Supplementary.pdf)

# Hard sample mining algorithm and ablation

<a id="appx-sample-mining"></a>

The motivation behind Dual-Stream Hard Sample Mining is driven by the STIT model’s specific failure modes and the optimization dynamics of Reinforcement Learning. After the STIT stage, the model acquires basic forecasting capabilities but suffers from critical precision deficits and formatting hallucinations. To address these, we introduce a sample selection strategy tailored specifically for RL in time series forecasting.

[Algorithm S1](D-sample-mining.md#alg-hard_mining) details the proposed **Priority-Based Dual-Stream Hard Sample Mining** strategy used to construct the RDFR dataset $`\mathcal{D}_{RDFR}`$. The process consists of four phases starting with initial inference and evaluation. It then bifurcates into two distinct selection streams: a *Syntactic Correction Stream* that prioritizes samples exhibiting formatting errors or low format scores ($`S_{fmt}`$) to ensure structural validity, and a *Semantic Reinforcement Stream* that targets “hard” samples with high MSE loss ($`L_{mse}`$) using a density-based binning approach to enhance prediction accuracy. Finally, the outputs of these streams are fused to create a balanced dataset for model optimization.

<a id="alg-hard_mining"></a>

### Algorithm S1: Priority-Based Dual-Stream Hard Sample Mining

```text
Input: training pairs D = {(x_i, y_i)}, STIT policy pi, quotas N_syn and N_sem
Output: RDFR training set D_RDFR

1. Inference and evaluation
   P_error = empty set
   For each (x_i, y_i) in D:
       Generate prediction y_hat_i using pi(x_i).
       Compute format score S_fmt_i and MSE loss L_mse_i.
       If a specified error pattern is detected (for example, a missing decimal point):
           Add (x_i, y_i) to P_error.

2. Syntactic correction
   If |P_error| > N_syn:
       D_syn = Sample(P_error, N_syn).
   Otherwise:
       N_remain = N_syn - |P_error|.
       P_rank = TopK(D excluding P_error, key = -S_fmt, k = N_remain).
       D_syn = union(P_error, P_rank).

3. Semantic reinforcement
   Compute mean MSE mu_mse over D.
   R_focus = {(x_i, y_i) in D where L_mse_i > mu_mse}.
   Partition R_focus into K bins based on MSE density.
   D_sem = empty set.
   For each bin k:
       Set n_k = N_sem * |Bin_k| / sum_j |Bin_j|.
       Add Sample(Bin_k, n_k) to D_sem.

4. Fusion
   D_RDFR = union(D_syn, D_sem).
   Return D_RDFR.
```

[Typeset algorithm and notation](../supplement/RDTU-Supplementary.pdf).

We avoid full-dataset RL training during the RDFR stage for two reasons: it introduces immense computational overhead, and more importantly, it dilutes targeted reward signals. Standard "easy" samples do not trigger structural or precision failures; thus, including them prevents the RL policy from focusing on critical errors. Our preliminary observations indicate that full-dataset RL training yields inferior performance compared to training exclusively on selected hard samples (See [Table S18](D-sample-mining.md#tab-rdfr_data_construction_ablation)). By actively filtering for samples that expose structural weaknesses (via the Syntactic Correction stream) and regression boundaries (via the Semantic Reinforcement stream), Dual-Stream Hard Sample Mining ensures the RDFR phase receives highly concentrated, informative reward signals. This targeted approach efficiently resolves the STIT model’s inherent flaws, directly enabling our superior forecasting performance.

<a id="tab-rdfr_data_construction_ablation"></a>

### Table S18

Ablation study on RDFR training data construction on ETTh1 with prediction horizon $`H=96`$. We compare RDFR trained on the full training set and the proposed Dual-Stream selected subset.

| RDFR Training Data | MSE ↓ | MAE ↓ | Training Time |
| --- | ---: | ---: | ---: |
| Full Dataset | 0.358 | 0.388 | >3h |
| Dual-Stream Selected (Ours) | 0.351 | 0.382 | 0.3h |

[Download table (CSV)](../data/rdfr_data_construction_ablation.csv).


To further validate the efficiency of the proposed Dual-Stream Hard Sample Mining strategy, we compare RDFR training using the full training set and the selected RDFR subset on ETTh1 with $`H=96`$. As shown in [Table S18](D-sample-mining.md#tab-rdfr_data_construction_ablation), training RDFR on the full dataset substantially increases the computational cost, requiring more than 3 hours, but does not bring additional performance gains. In contrast, the proposed Dual-Stream selected subset achieves lower MSE and MAE while reducing the RDFR training time to only 0.3 hours. This suggests that RDFR benefits more from targeted high-leverage samples than from simply increasing the amount of reinforcement learning data, supporting the necessity of the proposed data construction strategy.

---
Source: full manuscript Appendix D. See the [coverage map](coverage.md) and [source notes](source-notes.md).
