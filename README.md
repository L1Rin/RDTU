<div align="center">

# RDTU

### Does LLM-based Time Series Forecasting Really Need Pre-Alignment?

**Supplementary Materials**

Yuqing Wang · University of Cambridge

[**Complete PDF**](supplement/RDTU-Supplementary.pdf) · [**Reading Guide**](docs/index.md) · [**Full Results**](docs/B-forecasting-results.md) · [**Qualitative Gallery**](docs/E-qualitative-gallery.md)

</div>

<p align="center">
  <a href="assets/figures/Intro.pdf"><img src="assets/figures/Intro.png" width="850" alt="Comparison of alignment-based forecasting and RDTU's direct temporal unification paradigm"></a>
</p>

RDTU treats time series forecasting as numerical text generation. **Supervised Temporal Instruction Tuning (STIT)** establishes the forecasting format; **Reinforcement-Driven Forecasting Refinement (RDFR)** refines sequence length, numerical syntax and prediction accuracy.

This repository accompanies the ICASSP manuscript and restores the expanded explanations, experiments and appendices from the full manuscript. The material is available as **12 reading chapters, 18 tables with CSV exports, 23 vector figure assets, and a complete PDF**. Original numerical values, decimal precision and missing entries are preserved.

## Explore the supplementary material

| Topic | What you will find | Read |
| :--- | :--- | :--- |
| **Training and evaluation** | LoRA and GRPO settings, training budgets, dataset splits, metric definitions and three-seed statistical analyses | [Experimental details](docs/A-experimental-details.md) |
| **Long-term and short-term forecasting** | Every forecasting horizon, additional baselines, and M4 SMAPE / MASE / OWA by sampling interval | [Complete forecasting tables](docs/B-forecasting-results.md) |
| **Data efficiency and transfer** | 10% and 5% few-shot results; all eight ETT transfer directions; horizon and cross-domain generalization | [Generalization results](docs/C-generalization.md) |
| **Method and rewards** | Numerical serialization, the two-stage pipeline and the full reward equations | [Method details](docs/03-method.md) |
| **Hard sample mining** | Syntactic and semantic streams, complete pseudocode, and full-data versus selected-data ablation | [Algorithm and ablation](docs/D-sample-mining.md) |
| **Qualitative examples** | Length, accuracy and formatting comparisons for ETTh1, ETTh2 and ETTm1 | [ETTh1](docs/04-experiments.md#showcases-analysis) · [ETTh2 and ETTm1](docs/E-qualitative-gallery.md) |
| **Prompts** | The original multivariate instruction and example model response, including numerical strings | [Prompt example](docs/F-prompt.md) |
| **Context and scope** | Expanded related work, conclusion, future research scope and societal impacts | [Related work](docs/02-related-work.md) · [Discussion](docs/05-discussion.md) · [Impacts](docs/G-societal-impacts.md) |

## From STIT to RDFR

<p align="center">
  <a href="assets/figures/Method.pdf"><img src="assets/figures/Method.png" width="950" alt="RDTU training pipeline with supervised temporal instruction tuning followed by reinforcement-driven forecasting refinement"></a>
</p>

1. **Serialize the task.** Combine the forecasting role, domain metadata, historical observations and target horizon in a structured text prompt.
2. **Adapt the backbone.** Fine-tune Qwen2.5-7B-Instruct with STIT using the reported LoRA configuration.
3. **Refine numerical generation.** Select structural failures and difficult predictions, then train with length, format and accuracy rewards in a 1:1:8 ratio.

## Downloads

- [Complete supplementary PDF](supplement/RDTU-Supplementary.pdf)
- [All numerical tables in CSV](data/README.md)
- [Original vector figures and web previews](assets/figures/README.md)
- [LaTeX sources for the supplementary PDF](supplement/latex/README.md)
- [Bibliographic references](docs/references.md)

The [coverage map](docs/coverage.md) shows where the material removed or condensed from the full manuscript has been restored. The [source notes](docs/source-notes.md) document the final manuscript's zero-shot correction and inconsistencies in source-reported ranking summaries.

## Citation

```bibtex
@misc{wang_rdtu_supplementary,
  author = {Wang, Yuqing},
  title = {RDTU: Supplementary Materials for Does LLM-based Time Series Forecasting Really Need Pre-Alignment?},
  howpublished = {GitHub repository},
  url = {https://github.com/L1Rin/RDTU-Supplementary}
}
```
