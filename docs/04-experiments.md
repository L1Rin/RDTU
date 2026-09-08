[Home](../README.md) · [Reading guide](index.md) · [Complete PDF](../supplement/RDTU-Supplementary.pdf)

# Experiments and qualitative analysis

<a id="tab-long-term-forecasting-brief"></a>

### Table S1

**Long-term forecasting: horizon averages.** Lower values are better. Cells retain the numerical precision of the manuscript.

[Download all values (CSV)](../data/long-term-forecasting-brief-new.csv).

[![Long-term forecasting: horizon averages](../assets/tables/s01.png)](../assets/tables/s01.pdf)

[Original LaTeX table PDF](../assets/tables/s01.pdf)

<a id="tab-short-term-forecasting-brief"></a>

### Table S2

**M4 forecasting: weighted averages.** Lower values are better. Cells retain the numerical precision of the manuscript.

[Download all values (CSV)](../data/short-term-forecasting-brief.csv).

[![M4 forecasting: weighted averages](../assets/tables/s02.png)](../assets/tables/s02.pdf)

[Original LaTeX table PDF](../assets/tables/s02.pdf)

**Datasets.** We adopt 8 widely used MTS benchmarks: ETT (Electricity Transformer Temperature) [Zhou et al., 2021](references.md#zhou2021informer), including ETTh1, ETTh2, ETTm1, ETTm2; Weather [Wu et al., 2021](references.md#wu2021autoformer), Illness [Wu et al., 2021](references.md#wu2021autoformer), Traffic [Wu et al., 2021](references.md#wu2021autoformer), and Electricity [Trindade, 2015](references.md#electricity), which have been extensively adopted for benchmarking long-term forecasting models  [Wu et al., 2023](references.md#wu2022timesnet). The prediction horizon $`H`$ is set to {24, 36, 48, 60} for Illness, and {96, 192, 336, 720} for the remaining datasets.

**Baselines.** We compare RDTU with SOTA methods, categorized as follows: (1) **VLM-based models:** `Time-VLM`  [Zhong et al., 2025](references.md#zhong2025time); (2) **LVM-based models:** `VisionTS`  [Chen et al., 2024](references.md#chen2024visionts) and `DMMV-A`  [Shen et al., 2025](references.md#shen2025dmmv); (3) **LLM-based models:** `Time-LLM`  [Jin et al., 2024](references.md#jin2024timellm) and `GPT4TS`  [Zhou et al., 2023](references.md#zhou2023one); (4) **Transformer-based models:** `PatchTST`  [Nie et al., 2023](references.md#nie2022time), `FEDformer`  [Zhou et al., 2022](references.md#zhou2022fedformer), `Autoformer`  [Wu et al., 2021](references.md#wu2021autoformer), `Stationary`  [Liu et al., 2022](references.md#liu2022non), `ETSformer`  [Woo et al., 2022](references.md#woo2022etsformer), and `Informer`  [Zhou et al., 2021](references.md#zhou2021informer); (5) **Non-Transformer models:** `DLinear`  [Zeng et al., 2023](references.md#zeng2023transformers), `TimesNet`  [Wu et al., 2023](references.md#wu2022timesnet), and `CycleNet`  [Lin et al., 2024](references.md#lin2024cyclenet). In short-term forecasting, we compare our model with N-HiTS  [Challu et al., 2023](references.md#challu2023nhits) and N-BEATS  [Oreshkin et al., 2020](references.md#oreshkin2019n).

**Implementation.** We implement our framework using **Qwen2.5-7B-Instruct**  [Yang et al., 2024](references.md#qwen2.5) as the primary backbone.

All experiments are conducted on 8 **NVIDIA A100 (80GB)** GPUs. More details such as specific training expenses are shown in [Section](A-experimental-details.md#appx-implementation).

## Long-term Forecasting

<a id="sec-long-term-forecasting"></a>

**Setups.** We conduct extensive evaluations on eight widely-used real-world benchmarks: ETTh1, ETTh2, ETTm1, ETTm2, Weather, Electricity (ECL), Traffic, and ILI.

**Results.** [Table S1](04-experiments.md#tab-long-term-forecasting-brief) summarizes the long-term forecasting performance. **RDTU** achieves superior accuracy, securing the highest number of best results (**9 wins**) across all benchmarks. It achieves highly competitive state-of-the-art-level performance, while remaining competitive with the strongest specialized numerical and vision-based baselines. Notably, RDTU establishes a significant lead over the strongest language-based baselines, reducing MSE by approximately **5.5%** compared to Time-LLM on the *Electricity* dataset and **4.5%** versus GPT4TS on *ETTh1*. These results confirm that our direct unification strategy, devoid of alignment bottlenecks, captures complex temporal dependencies with greater precision than competing paradigms.

## Short-term Forecasting

**Setups.** We extend our evaluation to short-term forecasting using the M4 benchmark  [Makridakis et al., 2018](references.md#makridakis2018m4).

We employ Symmetric Mean Absolute Percentage Error (SMAPE), Mean Absolute Scaled Error (MASE), and Overall Weighted Average (OWA) as the evaluation metrics.

**Results.** As presented in [Table S2](04-experiments.md#tab-short-term-forecasting-brief), **RDTU** demonstrates robust short-horizon performance, achieving the lowest SMAPE of **11.979** and a state-of-the-art OWA of **0.859**. It significantly outperforms baselines like GPT4TS (OWA 0.940) and TimesNet (OWA 0.955), proving that our skip-alignment strategy effectively preserves local temporal details. Furthermore, RDTU surpasses specialized models such as N-HiTS and PatchTST (both OWA 0.869). While matching Time-LLM’s competitive performance, RDTU achieves these results via a more streamlined direct unification architecture, validating the efficacy of the RDFR system in optimizing precision across varying temporal scales.

<a id="tab-few-shot-forecasting-10per-brief"></a>

### Table S3

**Few-shot forecasting: 10% horizon averages.** Lower values are better. Cells retain the numerical precision of the manuscript.

[Download all values (CSV)](../data/few-shot-forecasting-part1-summary.csv).

[![Few-shot forecasting: 10% horizon averages](../assets/tables/s03.png)](../assets/tables/s03.pdf)

[Original LaTeX table PDF](../assets/tables/s03.pdf)

<a id="tab-zero-shot-forecasting-brief"></a>

### Table S4

**Zero-shot ETT transfer: horizon averages.** Lower values are better. Cells retain the numerical precision of the manuscript.

[Download all values (CSV)](../data/zero-shot-forecasting-brief-summary.csv).

[![Zero-shot ETT transfer: horizon averages](../assets/tables/s04.png)](../assets/tables/s04.pdf)

[Original LaTeX table PDF](../assets/tables/s04.pdf)

## Few-shot Forecasting

**Setups.** LLMs have demonstrated remarkable few-shot learning capabilities  [Liu et al., 2023](references.md#liu2023large). To evaluate the data efficiency of our framework in low-resource scenarios, we conduct few-shot learning experiments by restricting the training set to only $`10\%`$ of the available data.

**Results.** As reported in [Table S3](04-experiments.md#tab-few-shot-forecasting-10per-brief), **RDTU** exhibits exceptional few-shot capabilities, securing the best performance across all metrics (14 out of 14). While data scarcity severely impacts deep learning baselines like PatchTST (ETTh1 MSE 0.633), RDTU maintains a robust MSE of **0.551** on the same task. Moreover, it consistently outperforms adapter-based LLMs such as Time-LLM (0.556) and GPT4TS (0.590). This validates that our direct unification strategy effectively leverages the pre-trained backbone to mitigate overfitting, proving superior efficiency over complex auxiliary adapters in data-limited scenarios.

## Zero-shot Forecasting

**Setups.** To assess the generalization capability of our framework under distribution shifts, we conduct zero-shot learning experiments using the ETT dataset family.

**Results.** As reported in [Table S4](04-experiments.md#tab-zero-shot-forecasting-brief), **RDTU** demonstrates exceptional transferability, achieving the lowest horizon-averaged MSE in **7 of 8 transfer directions**. For $`ETTh2 \to ETTh1`$, RDTU obtains 0.480 MSE compared with 0.479 for Time-LLM, while its MAE is lower (0.471 versus 0.474). It highlights a fundamental advantage over supervised baselines, significantly outperforming Time-LLM in the $`ETTh1 \to ETTh2`$ transfer (MSE **0.344** vs. 0.353). Moreover, RDTU consistently surpasses competing LLM-based methods; in the challenging $`ETTh2 \to ETTh1`$ scenario, it maintains a robust MSE of **0.480**, far exceeding GPT4TS (0.757). These results support cross-dataset transfer within the evaluated ETT-family settings.

## Showcases Analysis

<a id="fig-showcase01-len"></a>

<a id="fig-showcase02-mse"></a>

<a id="fig-showcase03-fmt"></a>

<a id="fig-showcase01"></a>

<a id="fig-showcase02"></a>

<a id="fig-showcase03"></a>

<a id="fig-showcases"></a>

#### Prediction length

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Incomplete prediction (early stopping).](../assets/figures/showcase/ground_truth_plot_01_len.png)](../assets/figures/showcase/ground_truth_plot_01_len.pdf) | [![Correction of prediction length.](../assets/figures/showcase/ground_truth_plot_01.png)](../assets/figures/showcase/ground_truth_plot_01.pdf) |


#### Numerical accuracy

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Low prediction accuracy (high MSE).](../assets/figures/showcase/ground_truth_plot_03_mse.png)](../assets/figures/showcase/ground_truth_plot_03_mse.pdf) | [![Enhanced prediction precision.](../assets/figures/showcase/ground_truth_plot_03.png)](../assets/figures/showcase/ground_truth_plot_03.pdf) |


#### Output format

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Formatting error causing abnormal spikes.](../assets/figures/showcase/ground_truth_plot_05_decimal.png)](../assets/figures/showcase/ground_truth_plot_05_decimal.pdf) | [![Rectification of output format and outliers.](../assets/figures/showcase/ground_truth_plot_05.png)](../assets/figures/showcase/ground_truth_plot_05.pdf) |


**Figure S4.** Showcase visualizations of input-96-predict-96 results on the ETTh1 dataset. The top row (a–c) displays the baseline performance of the STIT model, which exhibits limitations in sequence length, accuracy, and output formatting. The bottom row (d–f) shows the improvements achieved after applying the proposed RDFR framework. More showcases are provided in [Section](E-qualitative-gallery.md#appx-showcase_addition).

To intuitively understand how our proposed *Temporal Refinement Reward System* in RDFR stage refines the model’s behavior, we visualize a comparison between the STIT baseline and the final RDTU model in [Figure S4](04-experiments.md#fig-showcases). This qualitative analysis targets three representative failure modes, validating the necessity of our composite reward system.

**Correction of Prediction Length** As observed in [Figure S4](04-experiments.md#fig-showcase01-len), the STIT model frequently suffers from "early stopping," failing to track the generation count and terminating the sequence before reaching the required horizon. This indicates a lack of internal counting logic. In contrast, [Figure S4](04-experiments.md#fig-showcase01) demonstrates the impact of the **Sequence Length Consistency Reward ($`R_{len}`$)**. By imposing a soft exponential length constraint, the RDFR stage forces the model to attend to the output length, ensuring the generated sequence perfectly matches the target horizon without truncation.

**Enhancement of Prediction Precision** [Figure S4](04-experiments.md#fig-showcase02-mse) illustrates a case where the STIT model captures the general trend direction but fits loosely to the ground truth, exhibiting high variance and failing to capture local volatility. This corresponds to the limitations of token-level tuning in forecasting tasks. [Figure S4](04-experiments.md#fig-showcase02) showcases the refinement achieved via the **Prediction Accuracy Reward ($`R_{acc}`$)**. With its exponential scaling, $`R_{acc}`$ penalizes even minor deviations in the high-precision regime, driving the model to produce a curve that hugs the ground truth tightly and significantly reducing the MSE.

**Rectification of Formatting and Outliers** Most critically, [Figure S4](04-experiments.md#fig-showcase03-fmt) reveals a severe "Integer Projection" hallucination where the STIT model fails to generate the decimal point (e.g., splitting a value like ‘3.21‘ into two tokens ‘3‘ and ‘21‘). This formatting error inserts an extreme outlier into the time series and causes a phase shift in all subsequent data points. [Figure S4](04-experiments.md#fig-showcase03) confirms that the **Format Compliance Reward ($`R_{fmt}`$)** effectively eliminates this issue. By penalizing the model step-by-step for missing floating-point structures, the RDFR system enforces strict adherence to numerical syntax, restoring the smooth, continuous trajectory of the time series and preventing catastrophic outliers.

## Ablation and Sensitivity Analysis

In this section, we perform comprehensive ablation studies to dissect the effectiveness of each component within the RDTU framework. Followed by [Jin et al., 2024](references.md#jin2024timellm), all experiments reported in this section are conducted on the **ETTh1** dataset with a fixed prediction horizon of $`H=96`$ unless otherwise explicitly stated.

**Component Analysis of the RDFR Framework.** To validate our design, we conducted an ablation study on the ETTh1 dataset. As shown in [Table S5](04-experiments.md#tab-ablation_02), while the off-the-shelf Qwen2.5-Instruct failed to generate valid outputs, the STIT model alone established a robust baseline with an MSE of **0.403**. This pivotal result demonstrates that complex pre-alignment modules are unnecessary; instruction tuning alone provides sufficient modality awareness for the LLM to function as a competent forecaster. Building on this foundation, the RDFR stage proved essential for precision. By imposing strict structural constraints and accuracy-driven rewards, the final RDTU framework further reduced the MSE to **0.351** with a **12.90%** improvement over the STIT baseline, confirming that reinforcement learning effectively bridges the gap between basic instruction following and high-precision regression.

<a id="tab-ablation_02"></a>

### Table S5

Ablation study of different reward components in the RDFR training stage. Improvements are computed relative to Qwen2.5-Instruct-STIT.

[![Ablation study of different reward components in the RDFR training stage](../assets/tables/s05.png)](../assets/tables/s05.pdf)

[Original LaTeX table PDF](../assets/tables/s05.pdf)

[Download table (CSV)](../data/ablation_02.csv).

<a id="fig-ablation_01"></a>

<a id="fig-ablation_03"></a>

<a id="fig-ablation_combined"></a>

[![Impact of the reward weight ratio.](../assets/figures/ablation/ablation01.png)](../assets/figures/ablation/ablation01.pdf)

[![Scaling laws on training efficiency and forecasting performance.](../assets/figures/ablation/ablation03_combined.png)](../assets/figures/ablation/ablation03_combined.pdf)

**Figure S5.** Ablation analysis of reward weighting and model scaling. Left: the red line represents the Mean Squared Error (MSE) on the excluded dataset, while the blue bars indicate the number of detected anomalies. Right: the line chart tracks MSE and MAE, showing that increased model capacity leads to consistent improvements in prediction accuracy.

**Impact of Reward Weight Ratios.** We investigate the optimal balance between structural constraints and regression precision by varying the accuracy reward weight $`\lambda_{acc}`$ (fixing $`\lambda_{len}:\lambda_{fmt}`$ at $`1:1`$). Results on ETTh1 identify $`\mathbf{1:1:8}`$ as the optimal configuration, achieving the lowest MSE of **0.351**. Deviating from this equilibrium degrades performance via two distinct failure modes: low weights ($`1:1:3`$) result in under-optimization of numerical values (MSE 0.377), while excessive weights ($`1:1:15`$) induce "structural collapse." As shown in [Figure S5](04-experiments.md#fig-ablation_01), pushing beyond the optimal threshold causes formatting anomalies to spike from 10 to 33, demonstrating that overpowering syntax constraints with accuracy objectives ultimately corrupts prediction validity.

**Impact of Model Scaling.** We evaluate the impact of model capacity across the Qwen2.5 family (0.5B, 1.5B, 3B, 7B). Results in [Figure S5](04-experiments.md#fig-ablation_03) reveal a robust scaling law: as parameter count increases, forecasting accuracy consistently improves, with MSE on ETTh1 monotonically decreasing from 0.365 (0.5B) to 0.351 (7B). This confirms that **RDTU** effectively harnesses the stronger reasoning capabilities of larger backbones to achieve finer precision.

---
Source: full manuscript Section 4. See the [coverage map](coverage.md) and [source notes](source-notes.md).
