[Home](../README.md) · [Reading guide](index.md) · [Complete PDF](../supplement/RDTU-Supplementary.pdf)

# Training, datasets, metrics and statistics

<a id="appx-implementation"></a>

## Implementation

For **Stage I (STIT)**, we utilize LoRA ($r=16, \alpha=32$) targeting query and value modules. Optimization is performed via AdamW (learning rate $2\times 10^{-4}$, global batch size 32) with a cosine annealing scheduler (0.03 warmup). In **Stage II (RDFR)**, we initialize the policy from the SFT checkpoint with a reduced learning rate of $5\times 10^{-6}$ and a KL-divergence coefficient $\beta_{kl}=0.04$. We configure the Group Size $G=8$, sampling 8 outputs per prompt. The total reward function $R_{total}$ combines length consistency ($R_{len}$), format compliance ($R_{fmt}$), and prediction accuracy ($R_{acc}$) with a strict ratio of 1:1:8 ($\lambda_{len}=0.1, \lambda_{fmt}=0.1, \lambda_{acc}=0.8$), prioritizing forecasting precision. Specifically, $R_{fmt}$ aggregates sub-goals (number, float, precision) with weights $\{0.2, 0.3, 0.5\}$, while sensitivity factors are set to $\alpha=0.5$ for length decay and $\beta=10.0$ for accuracy scaling.

#### Training Budget and Resource Usage.

To further clarify the practical cost of the proposed two-stage training pipeline, we report the per-dataset training budget and resource usage in [Table S6](A-experimental-details.md#tab-training_resource). Although RDTU adopts a 7B LLM backbone, the overall training cost remains moderate. For the STIT stage, training on standard long-term forecasting benchmarks requires only about 2.5–4.3 hours, with a peak memory usage of approximately 24 GB per GPU. More importantly, the RDFR stage introduces only a small additional overhead, requiring about 0.3–0.5 hours and approximately 32 GB peak memory per GPU. This confirms that the proposed reinforcement-driven refinement is a lightweight yet effective stage: it improves numerical precision and output validity without introducing extra pre-alignment modules or substantial architectural overhead.

<a id="tab-training_resource"></a>

### Table S6

Training settings and resource usage on different datasets.

| Dataset | Stage | Training Size | Epochs | Time (Hours) | Peak VRAM per GPU |
| --- | ---: | ---: | ---: | ---: | ---: |
| ETTh1 | STIT / RDFR | 8,545 / 425 | 15 / 3 | ≈2.5 / ≈0.3 | ≈24 GB / ≈32 GB |
| ETTh2 | STIT / RDFR | 8,545 / 425 | 15 / 3 | ≈2.5 / ≈0.3 | ≈24 GB / ≈32 GB |
| ETTm1 | STIT / RDFR | 34,465 / 1,713 | 5 / 2 | ≈4.3 / ≈0.5 | ≈24 GB / ≈32 GB |
| ETTm2 | STIT / RDFR | 34,465 / 1,713 | 5 / 2 | ≈4.3 / ≈0.5 | ≈24 GB / ≈32 GB |
| Electricity | STIT / RDFR | 18,317 / 911 | 8 / 3 | ≈3.7 / ≈0.5 | ≈24 GB / ≈32 GB |
| Traffic | STIT / RDFR | 12,185 / 606 | 10 / 3 | ≈3.0 / ≈0.3 | ≈24 GB / ≈32 GB |
| Weather | STIT / RDFR | 36,792 / 1,830 | 4 / 2 | ≈3.7 / ≈0.5 | ≈24 GB / ≈32 GB |

[Download table (CSV)](../data/training_resource.csv).


## Evaluation Metrics

For evaluation metrics, we utilize the mean square error (MSE) and mean absolute error (MAE) for long-term forecasting. In terms of the short-term forecasting on M4 benchmark, we adopt the symmetric mean absolute percentage error (SMAPE), mean absolute scaled error (MASE), and overall weighted average (OWA) as in N-BEATS [Oreshkin et al., 2020](references.md#oreshkin2019n). Note that OWA is a specific metric utilized in the M4 competition. The calculations of these metrics are as follows: <a id="equ-metrics"></a>

$$

\begin{aligned}
    \text{MSE} &= \frac{1}{H}\sum_{h=1}^H (\mathbf{Y}_{h} - \Hat{\mathbf{Y}}_{h})^2,
    &
    \text{MAE} &= \frac{1}{H}\sum_{h=1}^H|\mathbf{Y}_{h} - \Hat{\mathbf{Y}}_{h}|,\\
    \text{SMAPE} &= \frac{200}{H} \sum_{h=1}^H \frac{|\mathbf{Y}_{h} - \Hat{\mathbf{Y}}_{h}|}{|\mathbf{Y}_{h}| + |\Hat{\mathbf{Y}}_{h}|},
    &
    \text{MAPE} &= \frac{100}{H} \sum_{h=1}^H \frac{|\mathbf{Y}_{h} - \Hat{\mathbf{Y}}_{h}|}{|\mathbf{Y}_{h}|}, \\
    \text{MASE} &= \frac{1}{H} \sum_{h=1}^H \frac{|\mathbf{Y}_{h} - \Hat{\mathbf{Y}}_{h}|}{\frac{1}{H-s}\sum_{j=s+1}^{H}|\mathbf{Y}_j - \mathbf{Y}_{j-s}|},
    &
    \text{OWA} &= \frac{1}{2} \left[ \frac{\text{SMAPE}}{\text{SMAPE}_{\textrm{Naïve2}}}  + \frac{\text{MASE}}{\text{MASE}_{\textrm{Naïve2}}}  \right],
\end{aligned}

$$

where $s$ is the periodicity of the time series data. $H$ denotes the number of data points (i.e., prediction horizon in our cases). $\mathbf{Y}_{h}$ and $\Hat{\mathbf{Y}}_{h}$ are the $h$-th ground truth and prediction where $h \in \{1, \cdots, H\}$.

#### Declaration of LLM Usage.

LLMs are a core methodological component of this work. Specifically, we use Qwen2.5-Instruct as the backbone forecasting model and adapt it to time series forecasting through the proposed two-stage RDTU framework, including Supervised Temporal Instruction Tuning (STIT) and Reinforcement-Driven Forecasting Refinement (RDFR). The LLM is used to generate numerical time series predictions under structured prompts, while the training procedure, reward design, hyperparameters, and evaluation settings are documented in the paper and appendix.

## Dataset Details

<a id="tab-dataset"></a>

### Table S7

Dataset statistics are from [Wu et al., 2023](references.md#wu2022timesnet). The dimension indicates the number of time series (i.e., channels), and the dataset size is organized in (training, validation, testing).

| Tasks | Dataset | Dim. | Series Length | Dataset Size | Frequency | Domain |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Long-term / Forecasting | ETTm1 | 7 | [96, 192, 336, 720] | (34465, 11521, 11521) | 15 min | Temperature |
| Long-term / Forecasting | ETTm2 | 7 | [96, 192, 336, 720] | (34465, 11521, 11521) | 15 min | Temperature |
| Long-term / Forecasting | ETTh1 | 7 | [96, 192, 336, 720] | (8545, 2881, 2881) | 1 hour | Temperature |
| Long-term / Forecasting | ETTh2 | 7 | [96, 192, 336, 720] | (8545, 2881, 2881) | 1 hour | Temperature |
| Long-term / Forecasting | Electricity | 321 | [96, 192, 336, 720] | (18317, 2633, 5261) | 1 hour | Electricity |
| Long-term / Forecasting | Traffic | 862 | [96, 192, 336, 720] | (12185, 1757, 3509) | 1 hour | Transportation |
| Long-term / Forecasting | Weather | 21 | [96, 192, 336, 720] | (36792, 5271, 10540) | 10 min | Weather |
| Long-term / Forecasting | ILI | 7 | [24, 36, 48, 60] | (617, 74, 170) | 1 week | Illness |
| Short-term / Forecasting | M4-Yearly | 1 | 6 | (23000, 0, 23000) | Yearly | Demographic |
| Short-term / Forecasting | M4-Quarterly | 1 | 8 | (24000, 0, 24000) | Quarterly | Finance |
| Short-term / Forecasting | M4-Monthly | 1 | 18 | (48000, 0, 48000) | Monthly | Industry |
| Short-term / Forecasting | M4-Weekly | 1 | 13 | (359, 0, 359) | Weekly | Macro |
| Short-term / Forecasting | M4-Daily | 1 | 14 | (4227, 0, 4227) | Daily | Micro |
| Short-term / Forecasting | M4-Hourly | 1 | 48 | (414, 0, 414) | Hourly | Other |

[Download table (CSV)](../data/dataset.csv).


## Statistical Significance Analysis

<a id="sec-statistical_significance"></a>

<a id="tab-significance_main"></a>

### Table S8

Statistical significance analysis on representative long-term forecasting settings with $H=96$. We report mean and standard deviation over three independent runs with different random seeds. $p$-values are computed using a paired two-sided $t$-test between RDTU and Time-LLM over matched dataset-seed pairs.

| Dataset | Metric | RDTU | Time-LLM | Relative Gain | p-value |
| --- | ---: | ---: | ---: | ---: | ---: |
| ETTh1 | MSE / MAE | 0.352 ± 0.003 / 0.383 ± 0.002 | 0.376 ± 0.004 / 0.403 ± 0.003 | 6.38% / 4.96% | 0.018 / 0.021 |
| Electricity | MSE / MAE | 0.125 ± 0.002 / 0.211 ± 0.002 | 0.137 ± 0.002 / 0.233 ± 0.003 | 8.76% / 9.44% | 0.014 / 0.012 |
| Traffic | MSE / MAE | 0.359 ± 0.004 / 0.236 ± 0.003 | 0.393 ± 0.005 / 0.268 ± 0.004 | 8.65% / 11.94% | 0.011 / 0.009 |
| Average | MSE / MAE | 0.279 ± 0.003 / 0.277 ± 0.002 | 0.302 ± 0.004 / 0.301 ± 0.003 | 7.62% / 7.97% | 0.013 / 0.015 |

[Download table (CSV)](../data/significance_main.csv).


To examine whether the main performance gains are statistically reliable, we repeat RDTU and the strongest language-based baseline, Time-LLM, under three independent random seeds on representative long-term forecasting settings. We select ETTh1, Electricity, and Traffic because they cover different data scales and domains, including temperature, electricity consumption, and transportation. As shown in [Table S8](A-experimental-details.md#tab-significance_main), RDTU consistently achieves lower MSE and MAE across all selected datasets. The paired two-sided $t$-test over matched dataset-seed pairs yields statistically significant improvements, with average $p$-values of $0.013$ for MSE and $0.015$ for MAE. These results indicate that the observed superiority of RDTU over language-based baselines is stable across random seeds rather than being caused by incidental initialization effects.

<a id="tab-significance_rdfr"></a>

### Table S9

Statistical significance analysis of the RDFR stage on ETTh1 with $H=96$. We report mean and standard deviation over three independent runs. $p$-values are computed using a paired two-sided $t$-test between STIT and RDTU.

| Method | MSE ↓ | MAE ↓ | MSE Gain | MAE Gain |
| --- | ---: | ---: | ---: | ---: |
| Qwen2.5-Instruct-STIT | 0.403 ± 0.002 | 0.428 ± 0.002 | -- | -- |
| RDTU w/ RDFR | 0.351 ± 0.002 | 0.382 ± 0.002 | 12.90% | 10.75% |
| p-value | 0.004 | 0.006 | -- | -- |

[Download table (CSV)](../data/significance_rdfr.csv).


We further evaluate the statistical reliability of the RDFR stage, which is the key refinement component of RDTU. Specifically, we repeat both the STIT baseline and the final RDTU model under three independent random seeds on ETTh1 with $H=96$. As shown in [Table S9](A-experimental-details.md#tab-significance_rdfr), RDFR consistently improves the STIT baseline across all runs, reducing MSE from $0.403 \pm 0.002$ to $0.351 \pm 0.002$ and MAE from $0.428 \pm 0.002$ to $0.382 \pm 0.002$. The paired two-sided $t$-test gives $p=0.004$ for MSE and $p=0.006$ for MAE, confirming that the performance gain introduced by RDFR is statistically significant. This supports our claim that RDFR reliably bridges the gap between basic instruction-following ability and high-precision numerical forecasting.

---
Source: full manuscript Appendix A. See the [coverage map](coverage.md) and [source notes](source-notes.md).
