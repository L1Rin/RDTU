[Home](../README.md) · [Reading guide](index.md) · [Complete PDF](../supplement/RDTU-Supplementary.pdf)

# Full long-term and M4 results

<a id="appx-long-short-term"></a>

## Long-term Forecasting

By leveraging two-stage RDTU framework while bypassing pre-alignment, our method attains SOTA performance in **35** instances across eight time series benchmarks. This underscores the considerable potential of LLMs as robust and reliable time series forecasters.

[Table S10](B-forecasting-results.md#tab-long-term-forecasting-full) presents a comprehensive evaluation of long-term forecasting performance across eight benchmark datasets, categorizing baseline models by their input modality (Language, Multi-Modal, Visual, and Numerical).

<a id="tab-long-term-forecasting-full"></a>

### Table S10

**Full long-term forecasting results.** Lower values are better. Cells retain the numerical precision of the manuscript.

[Download all values (CSV)](../data/long-term-forecasting-full-new.csv).

[![Full long-term forecasting results](../assets/tables/s10.png)](../assets/tables/s10.pdf)

[Original LaTeX table PDF](../assets/tables/s10.pdf)

<a id="tab-long-term-forecasting-additional"></a>

### Table S11

**Long-term forecasting: additional baselines.** Lower values are better. Cells retain the numerical precision of the manuscript.

[Download all values (CSV)](../data/long-term-forecasting-additional.csv).

[![Long-term forecasting: additional baselines](../assets/tables/s11.png)](../assets/tables/s11.pdf)

[Original LaTeX table PDF](../assets/tables/s11.pdf)

[Table S11](B-forecasting-results.md#tab-long-term-forecasting-additional) presents an extensive evaluation of the proposed RDTU method against six state-of-the-art baseline models (Autoformer, Stationary, ETSformer, LightTS, Informer, and Reformer) across eight benchmark datasets. The experimental results clearly demonstrate the superior performance of RDTU for long-term time series forecasting.

As indicated by the bold red values, RDTU achieves the lowest Mean Squared Error (MSE) across the listed settings and the lowest Mean Absolute Error (MAE) in all but one individual horizon setting ($`H \in \{24, 36, 48, 60\}`$ for ILI and $`H \in \{96, 192, 336, 720\}`$ for other datasets). The quantitative summary at the bottom of the table confirms this dominance, with a source-reported "1st Count" of 40 for RDTU and 0 for each listed baseline. This count is retained as reported; it is distinct from the number of individual MSE and MAE cells in the table. While models such as LightTS and ETSformer occasionally yield the second-best results (highlighted in blue), RDTU consistently provides significant accuracy improvements.

## Short-term Forecasting

Our complete results on short-term forecasting are presented in [Table S12](B-forecasting-results.md#tab-short-term-forecasting).

[Table S12](B-forecasting-results.md#tab-short-term-forecasting) extends the analysis to short-term time series forecasting. Evaluation metrics including SMAPE, MASE, and OWA indicate that RDTU maintains its leading position. In the weighted average analysis across all sampling intervals (Yearly, Quarterly, Monthly, Others), RDTU records the best performance (e.g., Average OWA of 0.859), and matches Time-LLM on OWA while achieving lower SMAPE (OWA 0.859), significantly surpassing traditional methods like N-HiTS and N-BEATS.

<a id="tab-short-term-forecasting"></a>

### Table S12

**Full M4 short-term forecasting results.** Lower values are better. Cells retain the numerical precision of the manuscript.

[Download all values (CSV)](../data/short-term-forecasting.csv).

[![Full M4 short-term forecasting results](../assets/tables/s12.png)](../assets/tables/s12.pdf)

[Original LaTeX table PDF](../assets/tables/s12.pdf)

---
Source: full manuscript Appendix B. See the [coverage map](coverage.md) and [source notes](source-notes.md).
