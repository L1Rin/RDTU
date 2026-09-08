# Source notes

[Home](../README.md) · [Coverage map](coverage.md)

## Numerical transcription

The supplementary tables and CSV files use the numerical strings in the supplied full manuscript. Reported averages, decimal precision, missing entries and approximate training-cost values are preserved. The preparation of this repository did not rerun experiments or reconstruct predictions from the plotted curves.

The main PDF and online chapters reorganize wide tables by dataset. RDTU's row is emphasized for navigation; that emphasis does not mean it is the best result in every cell. Original first/second/third-place styling is replaced with this consistent row emphasis because some source styling and ranking summaries are inconsistent with the displayed numbers.

## Zero-shot interpretation in the final manuscript

The original narrative stated that RDTU was best in all eight ETT transfer scenarios. The final ICASSP narrative narrows this to **seven of eight directions by horizon-averaged MSE**. In **ETTh2 → ETTh1**, the source table gives RDTU **0.480 MSE** versus Time-LLM **0.479**, and RDTU **0.471 MAE** versus Time-LLM **0.474**. The supplement uses this corrected interpretation and retains all values.

The final compact transfer table displays seven rows. The omitted eighth direction, **ETTm2 → ETTm1**, is restored with all horizons and baselines in [Appendix C](C-generalization.md#tab-zero-shot-forecasting), and with the original average values in [Table S4](04-experiments.md#tab-zero-shot-forecasting-brief).

## Source-reported ranking counts

The original ranking footers are reproduced separately from the metric values. Their counting convention is not explicitly specified. For comparison, the following check counts each displayed MSE or MAE minimum, includes `Avg` rows and counts ties as a minimum for every tied model. This is a check of the supplied table, not a new experiment.

| Table | Original RDTU footer | Count of displayed metric minima under the stated convention |
| :--- | ---: | ---: |
| Full long-term comparison (S10) | 35 | 35 |
| Additional long-term baselines (S11) | 40 | 79 |
| Full 10% few-shot comparison (S13) | 58 | 56 |
| Full 5% few-shot comparison (S14) | 39 | 39 |

For **Weather, H = 720** in the additional-baseline table, the source lists RDTU **0.322 MAE** and ETSformer **0.288 MAE**. Consequently, the original blanket statement that RDTU is lowest on both metrics in every setting is narrowed in the supplementary explanation. These source values are preserved.

## Other editorial and layout decisions

- The related-work opening follows the final manuscript's description of direct generation with two-stage training, rather than restoring the original broad “first attempt” claim.
- Training costs marked as approximate in the source remain approximate. Reported means, standard deviations, test descriptions and p-values are transcribed; seed-level logs were not included in the supplied manuscript folders.
- M4 “Others” is retained as the source's aggregate category. Missing full-result entries retain the original `/` or `--` marker and are not filled from another table. A paired MSE / MAE cell displays a single missing-value marker when both metrics are unavailable; the CSV keeps both original entries.
- The prompt example deliberately includes ellipses from the source. Only the displayed timestamp and numerical rows are available in that example; no omitted observations or outputs were invented.
- The historical checklist records the original manuscript's author responses. Its code-release statements are historical plans and do not describe files in this supplementary-material release.

The original research claims and explanations are retained wherever they remain consistent with the displayed evidence. Changes above address specific source inconsistencies and presentation requirements.
