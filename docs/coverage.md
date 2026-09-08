# Coverage of the full manuscript

[Home](../README.md) · [Reading guide](index.md)

The comparison uses the active contents of `neurips_2026.tex` and `ICASSP2027_RDTU.tex` in the two supplied manuscript folders. A file remaining in the ICASSP folder is not counted as part of its main PDF unless the main document actually includes it. In particular, the independent related-work section and appendices are not included in the final ICASSP main document.

| Full-manuscript content | ICASSP main-document treatment | Supplementary destination |
| :--- | :--- | :--- |
| Section 1: expanded motivation and comparison of forecasting paradigms | Introduction shortened and revised; paradigm comparison figure removed | [Overview; Figure S1](01-overview.md) |
| Section 2: independent related-work discussion | Section include disabled; selected literature condensed into introduction | [Extended related work](02-related-work.md) |
| Section 3: complete method explanation and sampling workflow figure | Core method retained; sampling workflow figure and appendix pointers removed | [Method; Figure S3](03-method.md) |
| Main long-term summary table | Layout and presentation condensed in the final version | [Complete original summary; Table S1](04-experiments.md#tab-long-term-forecasting-brief) |
| M4 setup, three-metric summary and explanation | Reduced to an OWA statement | [Table S2 and short-term explanation](04-experiments.md#tab-short-term-forecasting-brief) |
| 10% few-shot summary with MSE, MAE and all baselines | Combined table retains MSE for three models | [Table S3 and full explanation](04-experiments.md#tab-few-shot-forecasting-10per-brief) |
| ETT zero-shot summary with MSE, MAE and eight directions | Combined table lists MSE for three models and seven directions | [All eight directions; Table S4](04-experiments.md#tab-zero-shot-forecasting-brief) |
| ETTh1 qualitative analysis: early stopping, high MSE and formatting errors | Entire qualitative subsection and six-panel figure removed | [ETTh1 analysis; Figure S4](04-experiments.md#showcases-analysis) |
| Main component, reward-ratio and model-scaling ablations | Retained in the final version | [Table S5 and Figure S5](04-experiments.md#ablation-and-sensitivity-analysis), included for context |
| Original conclusion's future research scope | Concluding scope sentence omitted | [Discussion](05-discussion.md) |
| Appendix A: implementation, budgets, metrics, dataset statistics, seed statistics and LLM-use statement | Not included in the final main document | [All Appendix A content; Tables S6–S9](A-experimental-details.md) |
| Appendix B: horizon-level long-term results, additional baselines and M4 interval-level results | Not included in the final main document | [All Appendix B content; Tables S10–S12](B-forecasting-results.md) |
| Appendix C: 10% / 5% few-shot results, full ETT transfer, length extrapolation and cross-domain transfer | Not included in the final main document | [All Appendix C content; Tables S13–S17](C-generalization.md) |
| Appendix D: complete dual-stream pseudocode and training-data ablation | Algorithm and full-data comparison absent | [All Appendix D content; Algorithm S1 and Table S18](D-sample-mining.md) |
| Appendix E: ETTh2 and ETTm1 qualitative comparisons and explanations | Not included in the final main document | [All Appendix E content; Figures S6–S7](E-qualitative-gallery.md) |
| Appendix F: original multivariate prompt and example response | Not included in the final main document | [All Appendix F content; Figure S8](F-prompt.md) |
| Appendix G: societal-impact discussion | Not included in the final main document | [All Appendix G content](G-societal-impacts.md) |
| Original submission checklist: author answers and justifications | Conference-specific checklist omitted | [Historical author responses](reporting-checklist.md) |

All active scientific figures, result/settings tables, equations and explanatory sections are represented. The complete method and several retained result summaries are included as context so that links and explanations remain self-contained. Bibliographic citations are linked to the [reference list](references.md).

Commented-out drafts, files under `tables/old`, unused figure variants, conference instructions, example author information and template acknowledgments are outside the active research content. The original source's claims that were narrowed or corrected in the final manuscript are handled in the [source notes](source-notes.md).
