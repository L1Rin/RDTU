# Original manuscript tables

[Home](../../README.md) · [All tables in one PDF](manuscript-tables.pdf)

These tables are rendered from the original LaTeX table environments in the supplied manuscripts. The previews are direct rasterizations of the vector PDF exports. Values, row and column order, grouping, missing entries and original color annotations are preserved.

`s01`–`s18` contain the expanded full-manuscript tables. `icassp01`–`icassp03` contain the final ICASSP manuscript tables. The original caption numbering is retained within each version. The [source notes](../../docs/source-notes.md) explain known numerical-ranking discrepancies.

| Version | Table | Content | PDF | Source |
| :--- | :--- | :--- | :--- | :--- |
| Full manuscript | 1 | Long-term forecasting: horizon averages | [Open](s01.pdf) | [LaTeX](latex/s01.tex) |
| Full manuscript | 2 | M4 forecasting: weighted averages | [Open](s02.pdf) | [LaTeX](latex/s02.tex) |
| Full manuscript | 3 | Few-shot forecasting: 10% horizon averages | [Open](s03.pdf) | [LaTeX](latex/s03.tex) |
| Full manuscript | 4 | Zero-shot ETT transfer: horizon averages | [Open](s04.pdf) | [LaTeX](latex/s04.tex) |
| Full manuscript | 5 | Ablation study of different reward components in the RDFR training stage | [Open](s05.pdf) | [LaTeX](latex/s05.tex) |
| Full manuscript | 6 | Training settings and resource usage on different datasets | [Open](s06.pdf) | [LaTeX](latex/s06.tex) |
| Full manuscript | 7 | Dataset statistics | [Open](s07.pdf) | [LaTeX](latex/s07.tex) |
| Full manuscript | 8 | Statistical significance analysis on representative long-term forecasting settings with H=96 | [Open](s08.pdf) | [LaTeX](latex/s08.tex) |
| Full manuscript | 9 | Statistical significance analysis of the RDFR stage on ETTh1 with H=96 | [Open](s09.pdf) | [LaTeX](latex/s09.tex) |
| Full manuscript | 10 | Full long-term forecasting results | [Open](s10.pdf) | [LaTeX](latex/s10.tex) |
| Full manuscript | 11 | Long-term forecasting: additional baselines | [Open](s11.pdf) | [LaTeX](latex/s11.tex) |
| Full manuscript | 12 | Full M4 short-term forecasting results | [Open](s12.pdf) | [LaTeX](latex/s12.tex) |
| Full manuscript | 13 | Full few-shot forecasting results: 10% training data | [Open](s13.pdf) | [LaTeX](latex/s13.tex) |
| Full manuscript | 14 | Full few-shot forecasting results: 5% training data | [Open](s14.pdf) | [LaTeX](latex/s14.tex) |
| Full manuscript | 15 | Full zero-shot ETT transfer results | [Open](s15.pdf) | [LaTeX](latex/s15.tex) |
| Full manuscript | 16 | Zero-shot length generalization of RDTU | [Open](s16.pdf) | [LaTeX](latex/s16.tex) |
| Full manuscript | 17 | Cross-domain zero-shot generalization results | [Open](s17.pdf) | [LaTeX](latex/s17.tex) |
| Full manuscript | 18 | Ablation study on RDFR training data construction on ETTh1 with prediction horizon H=96 | [Open](s18.pdf) | [LaTeX](latex/s18.tex) |
| ICASSP final | 1 | ICASSP long-term forecasting summary | [Open](icassp01.pdf) | [LaTeX](latex/icassp01.tex) |
| ICASSP final | 2 | ICASSP compact few-shot and zero-shot comparison | [Open](icassp02.pdf) | [LaTeX](latex/icassp02.tex) |
| ICASSP final | 3 | ICASSP reward-component ablation | [Open](icassp03.pdf) | [LaTeX](latex/icassp03.tex) |

The export wrapper isolates one table per page and crops surrounding whitespace. Caption whitespace is normalized for compilation. Two local layout fixes are applied: the full-manuscript ablation width is expanded to fit its original contents, and the dataset table’s short-term row span is corrected from seven to the six supplied rows. These fixes do not change any data. Bibliographic citations are resolved from the supplied bibliography.

The extracted table environments (with trailing whitespace removed) and the self-contained [export document](latex/render-all.tex) are included. Build with `tectonic latex/render-all.tex`; the build document also includes bibliography pages for citation resolution. The downloadable table PDFs contain only the cropped tables.
