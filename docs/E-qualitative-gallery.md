[Home](../README.md) · [Reading guide](index.md) · [Complete PDF](../supplement/RDTU-Supplementary.pdf)

# Additional qualitative comparisons

<a id="appx-showcase_addition"></a>

[Figure S6](E-qualitative-gallery.md#fig-showcases_add_01) and [Figure S7](E-qualitative-gallery.md#fig-showcases_add_02) presents more qualitative comparison showcases between the baseline STIT model and the proposed RDFR framework on the ETTh2 and ETTm1 dataset (input-96-predict-96). In [Figure S6](E-qualitative-gallery.md#fig-showcases_add_01), the top row (a-c) illustrates critical limitations in the baseline, including incomplete sequence generation due to early stopping, low forecasting accuracy, and severe formatting errors where missing decimal points result in extreme outliers (specifically, values like $`1.25`$ are erroneously output as $`125`$). In contrast, the bottom row (d-f) demonstrates that RDFR effectively rectifies these issues, ensuring complete prediction lengths, significantly enhanced precision, and the elimination of formatting-induced anomalies.

In [Figure S7](E-qualitative-gallery.md#fig-showcases_add_02), the top row highlights the limitations of the baseline STIT model, which suffers from incomplete sequence generation, low accuracy, and severe formatting hallucinations. Specifically, in case (c), the model generates an erroneous space after the decimal point (e.g., splitting $`-1.75`$ into $`-1`$ and $`75`$), which causes the parser to misinterpret the fractional component as a massive integer outlier. The bottom row demonstrates that the proposed RDFR framework effectively rectifies these syntactic, semantic, and structural issues, ensuring continuous and robust time series prediction.

<a id="fig-showcase01_add01-len"></a>

<a id="fig-showcase02_add01-mse"></a>

<a id="fig-showcase03_add01-fmt"></a>

<a id="fig-showcase01_add01"></a>

<a id="fig-showcase02_add01"></a>

<a id="fig-showcase03_add01"></a>

<a id="fig-showcases_add_01"></a>

#### Prediction length

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Incomplete prediction (early stopping).](../assets/figures/appendix/showcase_additional/ground_truth_plot_01_len.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_01_len.pdf) | [![Correction of prediction length.](../assets/figures/appendix/showcase_additional/ground_truth_plot_01.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_01.pdf) |


#### Numerical accuracy

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Low prediction accuracy (high MSE).](../assets/figures/appendix/showcase_additional/ground_truth_plot_02_mse.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_02_mse.pdf) | [![Enhanced prediction precision.](../assets/figures/appendix/showcase_additional/ground_truth_plot_02.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_02.pdf) |


#### Output format

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Formatting error causing abnormal spikes.](../assets/figures/appendix/showcase_additional/ground_truth_plot_03_decimal.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_03_decimal.pdf) | [![Rectification of output format and outliers.](../assets/figures/appendix/showcase_additional/ground_truth_plot_03.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_03.pdf) |


**Figure S6.** More showcases visualization of input-96-predict-96 results on the ETTh2 dataset. The top row (a-c) displays the baseline performance of the STIT model, which exhibits limitations in sequence length, accuracy, and output formatting. The bottom row (d-f) showcases the improvements achieved after applying the proposed RDFR framework on the corresponding samples.

<a id="fig-showcase01_add02-len"></a>

<a id="fig-showcase02_add02-mse"></a>

<a id="fig-showcase03_add02-fmt"></a>

<a id="fig-showcase01_add02"></a>

<a id="fig-showcase02_add02"></a>

<a id="fig-showcase03_add02"></a>

<a id="fig-showcases_add_02"></a>

#### Prediction length

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Incomplete prediction (early stopping).](../assets/figures/appendix/showcase_additional/ground_truth_plot_04_len.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_04_len.pdf) | [![Correction of prediction length.](../assets/figures/appendix/showcase_additional/ground_truth_plot_04.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_04.pdf) |


#### Numerical accuracy

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Low prediction accuracy (high MSE).](../assets/figures/appendix/showcase_additional/ground_truth_plot_05_mse.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_05_mse.pdf) | [![Enhanced prediction precision.](../assets/figures/appendix/showcase_additional/ground_truth_plot_05.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_05.pdf) |


#### Output format

| STIT | RDTU (STIT + RDFR) |
| --- | ---: |
| [![Formatting error causing abnormal spikes.](../assets/figures/appendix/showcase_additional/ground_truth_plot_06_decimal.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_06_decimal.pdf) | [![Rectification of output format and outliers.](../assets/figures/appendix/showcase_additional/ground_truth_plot_06.png)](../assets/figures/appendix/showcase_additional/ground_truth_plot_06.pdf) |


**Figure S7.** More showcases visualization of input-96-predict-96 results on the ETTm1 dataset. The top row (a-c) displays the baseline performance of the STIT model, which exhibits limitations in sequence length, accuracy, and output formatting. The bottom row (d-f) showcases the improvements achieved after applying the proposed RDFR framework on the corresponding samples.

---
Source: full manuscript Appendix E. See the [coverage map](coverage.md) and [source notes](source-notes.md).
