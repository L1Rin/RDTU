[Home](../README.md) · [Reading guide](index.md) · [Complete PDF](../supplement/RDTU-Supplementary.pdf)

# Method and reward design

## Overview

We propose **Reinforced Direct Temporal Unification (RDTU)**, a framework that exploits the intrinsic reasoning ability of Large Language Models (LLMs) for time series forecasting without complex modality alignment modules. As shown in [Figure S2](03-method.md#fig-method_framework), RDTU follows a progressive two-stage training pipeline. First, **Supervised Temporal Instruction Tuning (STIT)** builds structure-aware instruction data to endow the model with basic forecasting ability and domain-specific instruction following, as detailed in [Section](03-method.md#sec-stit). Second, **Reinforcement-Driven Forecasting Refinement (RDFR)** further improves regression precision through task-specific rewards that enforce output format and refine prediction accuracy, as described in [Section](03-method.md#sec-rdfr).

## Supervised Temporal Instruction Tuning

<a id="sec-stit"></a>

To establish foundational capabilities for time-series reasoning and strict instruction adherence, we initiate the pipeline with **Supervised Temporal Instruction Tuning (STIT)**. Diverging from methods that rely on auxiliary encoders, we employ a direct serialization strategy where historical numerical data is transformed into discrete text strings. These sequences are seamlessly integrated into a structured natural language prompt composed of four semantic elements: an expert persona definition, domain-specific metadata, the serialized historical sequence, and the specific prediction directive. This unified textual format allows the pre-trained LLM backbone to be fine-tuned directly via standard causal language modeling, as detailed in [Section](F-prompt.md#appx-prompt).

<a id="fig-method_framework"></a>

[![The overall architecture of the RDTU framework. The pipeline proceeds in two stages: (1) Supervised Temporal Instruction Tuning (STIT) initializes the model with foundational forecasting capabilities via structured prompts; (2) Reinforcement-Driven Forecasting Refinement (RDFR) employs a Reinforcement Learning system to enforce numerical precision and formatting constraints.](../assets/figures/Method.png)](../assets/figures/Method.pdf)

**Figure S2.** The overall architecture of the **RDTU** framework. The pipeline proceeds in two stages: **(1) Supervised Temporal Instruction Tuning (STIT)** initializes the model with foundational forecasting capabilities via structured prompts; **(2) Reinforcement-Driven Forecasting Refinement (RDFR)** employs a Reinforcement Learning system to enforce numerical precision and formatting constraints.

## Reinforcement-Driven Forecasting Refinement

<a id="sec-rdfr"></a> While STIT provides a good initialization, the model often struggles with strict numerical output regarding the formats and long-horizon precision. To address these residual issues, we introduce the **RDFR** system, which is composed of two core contributions: a *Priority-Based Dual-Stream Hard Sample Mining* strategy for constructing high-leverage RDFR training data, and a *Temporal Refinement Reward System* designed to guide the optimization process.

### RDFR Data Construction Strategy

To address the instruction-following failures and precision deficits that persist after the STIT stage, we propose a **Priority-Based Dual-Stream Hard Sample Mining** strategy. As illustrated in [Figure S3](03-method.md#fig-RDFR), we decouple the data selection into two parallel streams, Syntactic Correction ($`\mathcal{D}_{syn}`$) and Semantic Reinforcement ($`\mathcal{D}_{sem}`$), which are unified to form the final Reinforcement-Driven Forecasting Refinement Dataset $`\mathcal{D}_{RDFR} = \mathcal{D}_{syn} \cup \mathcal{D}_{sem}`$. The complete algorithm of data construction strategy is shown in [Section](D-sample-mining.md#appx-sample-mining).

#### Syntactic Correction Stream.

The primary motivation of this stream is to eliminate "formatting hallucinations," such as non-numerical outputs or sequence length inconsistencies, which render predictions invalid. To quantify structural integrity, we define a format completeness score $`S_{fmt}`$:

```math
S_{fmt}^{(i)} = \mathbb{I}_{\text{valid}}(\hat{y}_i) \times \left( 1 - \min\left(1, \frac{|L_{pred}^{(i)} - L_{target}|}{L_{target}}\right) \right)
```

where $`\hat{y}_i`$ is the predicted sequence, and $`\mathbb{I}_{\text{valid}}`$ is a binary indicator that returns 0 if forbidden patterns are detected. The term involving $`L_{pred}^{(i)}`$ and $`L_{target}`$ penalizes deviations from the ground-truth sequence length. We construct $`\mathcal{D}_{syn}`$ by prioritizing samples with the lowest $`S_{fmt}`$ scores, effectively forcing the model to confront its most severe structural failures.

To construct $`\mathcal{D}_{syn}`$, the algorithm does not rely solely on ranking samples by their format scores ($`S_{fmt}`$); it also actively detects and prioritizes specific failure patterns (e.g., missing decimal points) to enhance the model’s targeted correction capabilities against severe structural errors.

For the complete algorithmic procedure and implementation details, please refer to [Section](D-sample-mining.md#appx-sample-mining).

#### Semantic Reinforcement Stream.

To refine regression accuracy without overfitting to outliers, this stream targets "hard" yet representative samples. We employ a *Density-Aware Stratified Sampling* strategy on the error manifold. Focusing on samples where the error exceeds the population mean ($`L_{mse}^{(i)} \gt  \mu`$), we partition the error distribution into $`K`$ bins and assign sampling quotas proportional to density:

```math
n_k = N_{sem} \times \frac{|\text{Bin}_k|}{\sum_{j=1}^{K} |\text{Bin}_j|}
```

Here, $`n_k`$ represents the number of samples drawn from the $`k`$-th error interval based on the total semantic budget $`N_{sem}`$, and $`|\text{Bin}_k|`$ denotes the sample count in that interval. This ensures $`\mathcal{D}_{sem}`$ captures the diverse modes of numerical difficulty inherent in the STIT model.

<a id="fig-RDFR"></a>

[![Priority-Based Dual-Stream Hard Sample Mining strategy](../assets/figures/RDFR.png)](../assets/figures/RDFR.pdf)

**Figure S3.** Priority-Based Dual-Stream Hard Sample Mining strategy

### Temporal Refinement Reward System

To align the model’s policy with the standards of time-series forecasting, we employ Group Relative Policy Optimization (GRPO)  [DeepSeek-AI et al., 2025](references.md#deepseekai2025deepseekr1) as our Reinforcement Forecasting Refinement framework. Therefore, we design a forecasting refinement reward function $`R_{total}`$ comprising three distinct components, each targeting a specific failure mode observed in STIT models.

#### Sequence Length Consistency Reward ($`R_{len}`$).

To mitigate "counting failures" where models drift from the required horizon, we replace standard linear penalties, which often lack sensitivity to "off-by-one" errors, with a non-linear exponential penalty. This acts as a soft constraint, imposing sharp penalties for minimal deviations to enforce rapid convergence to the target length $`L_{target}`$:

```math
R_{len} = \exp(-\alpha \cdot |L_{pred} - L_{target}|)
```

where $`\alpha`$ controls reward sensitivity, ensuring exact length adherence for high scores.

#### Format Compliance Reward ($`R_{fmt}`$).

To overcome the "sparse signal" problem where binary validity checks fail to distinguish between total hallucination and minor formatting errors, we employ *reward shaping*. We decompose structural compliance into progressive sub-goals to provide dense gradient feedback:


```math
\begin{aligned} R_{fmt} = \frac{1}{N} \sum_{i=1}^{N} \Big(&w_1 \cdot \mathbb{I}(\texttt{is\_number}_i) \\ &+w_2 \cdot \mathbb{I}(\texttt{is\_float}_i)+w_3 \cdot \mathbb{I}(\texttt{precision}_i)\Big) \end{aligned}
```

where $`N`$ represents the total number of predicted numerical values, and the indicator functions $`\mathbb{I}(\cdot)`$ verify token-level adherence to numeric character usage, decimal presence, and strict decimal precision as specified by the task, respectively, weighted by $`w_{\{1,2,3\}}`$.

#### Prediction Accuracy Reward ($`R_{acc}`$).

Since unbounded MSE loss can destabilize reward distributions and lacks sensitivity in high-precision regimes, we map the error to a bounded $`(0, 1]`$ interval via exponential decay. This ensures distinct feedback even as the model approaches saturation:

```math
R_{acc} = \exp(-\beta \cdot \text{MSE}(Y_{pred}, Y_{gt}))
```

where $`\beta`$ regulates the strictness of the accuracy requirement, preventing outlier dominance while maintaining significant gradient magnitude for small improvements.

The final reward is computed as a weighted sum $`R_{total} = \lambda_{len} R_{len} + \lambda_{fmt} R_{fmt} + \lambda_{acc} R_{acc}`$, balancing structural validity with regression precision.

---
Source: full manuscript Section 3. See the [coverage map](coverage.md) and [source notes](source-notes.md).
