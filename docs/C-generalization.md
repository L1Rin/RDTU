[Home](../README.md) · [Reading guide](index.md) · [Complete PDF](../supplement/RDTU-Supplementary.pdf)

# Few-shot, zero-shot and length generalization

<a id="appx-few-zero-shot"></a>

## Few-Shot Forecasting

<a id="tab-few-shot-forecasting-10per-full"></a>

### Table S13

**Full few-shot forecasting results: 10% training data.** Lower values are better. Cells retain the numerical precision of the manuscript.

Each cell is **MSE / MAE**. `Avg` denotes the source-reported average over horizons. A single `/` or `--` indicates that both metrics are unavailable in the source.

[Download all values (CSV)](../data/few-shot-forecasting-part1-full.csv).


#### ETTh1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.443 / 0.451 | 0.482 / 0.479 | 0.585 / 0.536 | 0.694 / 0.587 | 0.551 / 0.513 |
| Time-LLM | 0.448 / 0.460 | 0.484 / 0.483 | 0.589 / 0.540 | 0.700 / 0.604 | 0.556 / 0.522 |
| GPT4TS | 0.458 / 0.456 | 0.570 / 0.516 | 0.608 / 0.535 | 0.725 / 0.591 | 0.590 / 0.525 |
| DLinear | 0.492 / 0.495 | 0.565 / 0.538 | 0.721 / 0.622 | 0.986 / 0.743 | 0.691 / 0.600 |
| PatchTST | 0.516 / 0.485 | 0.598 / 0.524 | 0.657 / 0.550 | 0.762 / 0.610 | 0.633 / 0.542 |
| TimesNet | 0.861 / 0.628 | 0.797 / 0.593 | 0.941 / 0.648 | 0.877 / 0.641 | 0.869 / 0.628 |
| FEDformer | 0.512 / 0.499 | 0.624 / 0.555 | 0.691 / 0.574 | 0.728 / 0.614 | 0.639 / 0.561 |
| Autoformer | 0.613 / 0.552 | 0.722 / 0.598 | 0.750 / 0.619 | 0.721 / 0.616 | 0.702 / 0.596 |
| Stationary | 0.918 / 0.639 | 0.915 / 0.629 | 0.939 / 0.644 | 0.887 / 0.645 | 0.915 / 0.639 |
| ETSformer | 1.112 / 0.806 | 1.155 / 0.823 | 1.179 / 0.832 | 1.273 / 0.874 | 1.180 / 0.834 |
| LightTS | 1.298 / 0.838 | 1.322 / 0.854 | 1.347 / 0.870 | 1.534 / 0.947 | 1.375 / 0.877 |
| Informer | 1.179 / 0.792 | 1.199 / 0.806 | 1.202 / 0.811 | 1.217 / 0.825 | 1.199 / 0.809 |
| Reformer | 1.184 / 0.790 | 1.295 / 0.850 | 1.294 / 0.854 | 1.223 / 0.838 | 1.249 / 0.833 |


#### ETTh2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.271 / 0.322 | 0.369 / 0.367 | 0.402 / 0.423 | 0.425 / 0.443 | 0.367 / 0.389 |
| Time-LLM | 0.275 / 0.326 | 0.374 / 0.373 | 0.406 / 0.429 | 0.427 / 0.449 | 0.370 / 0.394 |
| GPT4TS | 0.331 / 0.374 | 0.402 / 0.411 | 0.406 / 0.433 | 0.449 / 0.464 | 0.397 / 0.421 |
| DLinear | 0.357 / 0.411 | 0.569 / 0.519 | 0.671 / 0.572 | 0.824 / 0.648 | 0.605 / 0.538 |
| PatchTST | 0.353 / 0.389 | 0.403 / 0.414 | 0.426 / 0.441 | 0.477 / 0.480 | 0.415 / 0.431 |
| TimesNet | 0.378 / 0.409 | 0.490 / 0.467 | 0.537 / 0.494 | 0.510 / 0.491 | 0.479 / 0.465 |
| FEDformer | 0.382 / 0.416 | 0.478 / 0.474 | 0.504 / 0.501 | 0.499 / 0.509 | 0.466 / 0.475 |
| Autoformer | 0.413 / 0.451 | 0.474 / 0.477 | 0.547 / 0.543 | 0.516 / 0.523 | 0.488 / 0.499 |
| Stationary | 0.389 / 0.411 | 0.473 / 0.455 | 0.507 / 0.480 | 0.477 / 0.472 | 0.462 / 0.455 |
| ETSformer | 0.678 / 0.619 | 0.785 / 0.666 | 0.839 / 0.694 | 1.273 / 0.874 | 0.894 / 0.713 |
| LightTS | 2.022 / 1.006 | 2.329 / 1.104 | 2.453 / 1.122 | 3.816 / 1.407 | 2.655 / 1.160 |
| Informer | 3.837 / 1.508 | 3.856 / 1.513 | 3.952 / 1.526 | 3.842 / 1.503 | 3.872 / 1.513 |
| Reformer | 3.788 / 1.533 | 3.552 / 1.483 | 3.395 / 1.526 | 3.205 / 1.401 | 3.485 / 1.486 |


#### ETTm1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.343 / 0.386 | 0.375 / 0.411 | 0.410 / 0.424 | 0.478 / 0.473 | 0.402 / 0.424 |
| Time-LLM | 0.346 / 0.388 | 0.373 / 0.416 | 0.413 / 0.426 | 0.485 / 0.476 | 0.404 / 0.427 |
| GPT4TS | 0.390 / 0.404 | 0.429 / 0.423 | 0.469 / 0.439 | 0.569 / 0.498 | 0.464 / 0.441 |
| DLinear | 0.352 / 0.392 | 0.382 / 0.412 | 0.419 / 0.434 | 0.490 / 0.477 | 0.411 / 0.429 |
| PatchTST | 0.410 / 0.419 | 0.437 / 0.434 | 0.476 / 0.454 | 0.681 / 0.556 | 0.501 / 0.466 |
| TimesNet | 0.583 / 0.501 | 0.630 / 0.528 | 0.725 / 0.568 | 0.769 / 0.549 | 0.677 / 0.537 |
| FEDformer | 0.578 / 0.518 | 0.617 / 0.546 | 0.998 / 0.775 | 0.693 / 0.579 | 0.722 / 0.605 |
| Autoformer | 0.774 / 0.614 | 0.754 / 0.592 | 0.869 / 0.677 | 0.810 / 0.630 | 0.802 / 0.628 |
| Stationary | 0.761 / 0.568 | 0.781 / 0.574 | 0.803 / 0.587 | 0.844 / 0.581 | 0.797 / 0.578 |
| ETSformer | 0.911 / 0.688 | 0.955 / 0.703 | 0.991 / 0.719 | 1.062 / 0.747 | 0.980 / 0.714 |
| LightTS | 0.921 / 0.682 | 0.957 / 0.701 | 0.998 / 0.716 | 1.007 / 0.719 | 0.971 / 0.705 |
| Informer | 1.162 / 0.785 | 1.172 / 0.793 | 1.227 / 0.908 | 1.207 / 0.797 | 1.192 / 0.821 |
| Reformer | 1.442 / 0.847 | 1.444 / 0.862 | 1.450 / 0.866 | 1.366 / 0.850 | 1.426 / 0.856 |


#### ETTm2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.174 / 0.260 | 0.236 / 0.308 | 0.272 / 0.323 | 0.413 / 0.384 | 0.274 / 0.319 |
| Time-LLM | 0.177 / 0.261 | 0.241 / 0.314 | 0.274 / 0.327 | 0.417 / 0.390 | 0.277 / 0.323 |
| GPT4TS | 0.188 / 0.269 | 0.251 / 0.309 | 0.307 / 0.346 | 0.426 / 0.417 | 0.293 / 0.335 |
| DLinear | 0.213 / 0.303 | 0.278 / 0.345 | 0.338 / 0.385 | 0.436 / 0.440 | 0.316 / 0.368 |
| PatchTST | 0.191 / 0.274 | 0.252 / 0.317 | 0.306 / 0.353 | 0.433 / 0.427 | 0.296 / 0.343 |
| TimesNet | 0.212 / 0.285 | 0.270 / 0.323 | 0.323 / 0.353 | 0.474 / 0.449 | 0.320 / 0.353 |
| FEDformer | 0.291 / 0.399 | 0.307 / 0.379 | 0.543 / 0.559 | 0.712 / 0.614 | 0.463 / 0.488 |
| Autoformer | 0.352 / 0.454 | 0.694 / 0.691 | 2.408 / 1.407 | 1.913 / 1.166 | 1.342 / 0.930 |
| Stationary | 0.229 / 0.308 | 0.291 / 0.343 | 0.348 / 0.376 | 0.461 / 0.438 | 0.332 / 0.366 |
| ETSformer | 0.331 / 0.430 | 0.400 / 0.464 | 0.469 / 0.498 | 0.589 / 0.557 | 0.447 / 0.487 |
| LightTS | 0.813 / 0.688 | 1.008 / 0.768 | 1.031 / 0.775 | 1.096 / 0.791 | 0.987 / 0.756 |
| Informer | 3.203 / 1.407 | 3.112 / 1.387 | 3.255 / 1.421 | 3.909 / 1.543 | 3.370 / 1.440 |
| Reformer | 4.195 / 1.628 | 4.042 / 1.601 | 3.963 / 1.585 | 3.711 / 1.532 | 3.978 / 1.587 |


#### Weather

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.159 / 0.209 | 0.199 / 0.244 | 0.257 / 0.292 | 0.311 / 0.335 | 0.232 / 0.270 |
| Time-LLM | 0.161 / 0.210 | 0.204 / 0.248 | 0.261 / 0.302 | 0.309 / 0.332 | 0.234 / 0.273 |
| GPT4TS | 0.163 / 0.215 | 0.210 / 0.254 | 0.256 / 0.292 | 0.321 / 0.339 | 0.238 / 0.275 |
| DLinear | 0.171 / 0.224 | 0.215 / 0.263 | 0.258 / 0.299 | 0.320 / 0.346 | 0.241 / 0.283 |
| PatchTST | 0.165 / 0.215 | 0.210 / 0.257 | 0.259 / 0.297 | 0.332 / 0.346 | 0.242 / 0.279 |
| TimesNet | 0.184 / 0.230 | 0.245 / 0.283 | 0.305 / 0.321 | 0.381 / 0.371 | 0.279 / 0.301 |
| FEDformer | 0.188 / 0.253 | 0.250 / 0.304 | 0.312 / 0.346 | 0.387 / 0.393 | 0.284 / 0.324 |
| Autoformer | 0.221 / 0.297 | 0.270 / 0.322 | 0.320 / 0.351 | 0.390 / 0.396 | 0.300 / 0.342 |
| Stationary | 0.192 / 0.234 | 0.269 / 0.295 | 0.370 / 0.357 | 0.441 / 0.405 | 0.318 / 0.323 |
| ETSformer | 0.199 / 0.272 | 0.279 / 0.332 | 0.356 / 0.386 | 0.437 / 0.448 | 0.318 / 0.360 |
| LightTS | 0.217 / 0.269 | 0.259 / 0.304 | 0.303 / 0.334 | 0.377 / 0.382 | 0.289 / 0.322 |
| Informer | 0.374 / 0.401 | 0.552 / 0.478 | 724 / 0.541 | 0.739 / 0.558 | 0.597 / 0.495 |
| Reformer | 0.335 / 0.380 | 0.522 / 0.462 | 0.715 / 0.535 | 0.611 / 0.500 | 0.546 / 0.469 |


#### Electricity

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.141 / 0.237 | 0.153 / 0.247 | 0.171 / 0.269 | 0.227 / 0.318 | 0.173 / 0.268 |
| Time-LLM | 0.139 / 0.241 | 0.151 / 0.248 | 0.169 / 0.270 | 0.240 / 0.322 | 0.175 / 0.270 |
| GPT4TS | 0.139 / 0.237 | 0.156 / 0.252 | 0.175 / 0.270 | 0.233 / 0.317 | 0.176 / 0.269 |
| DLinear | 0.150 / 0.253 | 0.164 / 0.264 | 0.181 / 0.282 | 0.223 / 0.321 | 0.180 / 0.280 |
| PatchTST | 0.140 / 0.238 | 0.160 / 0.255 | 0.180 / 0.276 | 0.241 / 0.323 | 0.180 / 0.273 |
| TimesNet | 0.299 / 0.373 | 0.305 / 0.379 | 0.319 / 0.391 | 0.369 / 0.426 | 0.323 / 0.392 |
| FEDformer | 0.231 / 0.323 | 0.261 / 0.356 | 0.360 / 0.445 | 0.530 / 0.585 | 0.346 / 0.427 |
| Autoformer | 0.261 / 0.348 | 0.338 / 0.406 | 0.410 / 0.474 | 0.715 / 0.685 | 0.431 / 0.478 |
| Stationary | 0.420 / 0.466 | 0.411 / 0.459 | 0.434 / 0.473 | 0.510 / 0.521 | 0.444 / 0.480 |
| ETSformer | 0.599 / 0.587 | 0.620 / 0.598 | 0.662 / 0.619 | 0.757 / 0.664 | 0.660 / 0.617 |
| LightTS | 0.350 / 0.425 | 0.376 / 0.448 | 0.428 / 0.485 | 0.611 / 0.597 | 0.441 / 0.489 |
| Informer | 1.259 / 0.919 | 1.160 / 0.873 | 1.157 / 0.872 | 1.203 / 0.898 | 1.195 / 0.891 |
| Reformer | 0.993 / 0.784 | 0.938 / 0.753 | 0.925 / 0.745 | 1.004 / 0.790 | 0.965 / 0.768 |


#### Traffic

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.405 / 0.288 | 0.412 / 0.292 | 0.424 / 0.306 | 0.463 / 0.325 | 0.426 / 0.303 |
| Time-LLM | 0.418 / 0.291 | 0.414 / 0.296 | 0.421 / 0.311 | 0.462 / 0.327 | 0.429 / 0.306 |
| GPT4TS | 0.414 / 0.297 | 0.426 / 0.301 | 0.434 / 0.303 | 0.487 / 0.337 | 0.440 / 0.310 |
| DLinear | 0.419 / 0.298 | 0.434 / 0.305 | 0.449 / 0.313 | 0.484 / 0.336 | 0.447 / 0.313 |
| PatchTST | 0.403 / 0.289 | 0.415 / 0.296 | 0.426 / 0.304 | 0.474 / 0.331 | 0.430 / 0.305 |
| TimesNet | 0.719 / 0.416 | 0.748 / 0.428 | 0.853 / 0.471 | 1.485 / 0.825 | 0.951 / 0.535 |
| FEDformer | 0.639 / 0.400 | 0.637 / 0.416 | 0.655 / 0.427 | 0.722 / 0.456 | 0.663 / 0.425 |
| Autoformer | 0.672 / 0.405 | 0.727 / 0.424 | 0.749 / 0.454 | 0.847 / 0.499 | 0.749 / 0.446 |
| Stationary | 1.412 / 0.802 | 1.419 / 0.806 | 1.443 / 0.815 | 1.539 / 0.837 | 1.453 / 0.815 |
| ETSformer | 1.643 / 0.855 | 1.641 / 0.854 | 1.711 / 0.878 | 2.660 / 1.157 | 1.914 / 0.936 |
| LightTS | 1.157 / 0.636 | 1.207 / 0.661 | 1.334 / 0.713 | 1.292 / 0.726 | 1.248 / 0.684 |
| Informer | 1.557 / 0.821 | 1.454 / 0.765 | 1.521 / 0.812 | 1.605 / 0.846 | 1.534 / 0.811 |
| Reformer | 1.527 / 0.815 | 1.538 / 0.817 | 1.550 / 0.819 | 1.588 / 0.833 | 1.551 / 0.821 |


#### Source-reported ranking summary

The following footer is transcribed from the original table. See [source notes](source-notes.md) for the counting convention and known source inconsistencies.

| Model | Reported count |
| --- | ---: |
| RDTU | 58 |
| Time-LLM | 8 |
| GPT4TS | 7 |
| DLinear | 1 |
| PatchTST | 1 |
| TimesNet | 0 |
| FEDformer | 0 |
| Autoformer | 0 |
| Stationary | 0 |
| ETSformer | 0 |
| LightTS | 0 |
| Informer | 0 |
| Reformer | 0 |


[Table S13](C-generalization.md#tab-few-shot-forecasting-10per-full) evaluates data efficiency through few-shot learning on 10% training data. In this data-scarce regime, RDTU exhibits dominant generalization capabilities, with a source-reported “1st Count” of 58, while Time-LLM has a reported count of 8. The repository source notes distinguish this reported footer from a direct count of the displayed numerical minima.

<a id="tab-few-shot-forecasting-5per-full"></a>

### Table S14

**Full few-shot forecasting results: 5% training data.** Lower values are better. Cells retain the numerical precision of the manuscript.

Each cell is **MSE / MAE**. `Avg` denotes the source-reported average over horizons. A single `/` or `--` indicates that both metrics are unavailable in the source.

[Download all values (CSV)](../data/few-shot-forecasting-part2-full-new.csv).


#### ETTh1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.479 / 0.460 | 0.624 / 0.536 | 0.741 / 0.603 | - / - | 0.615 / 0.535 |
| Time-LLM | 0.483 / 0.464 | 0.629 / 0.540 | 0.768 / 0.626 | - / - | 0.627 / 0.543 |
| GPT4TS | 0.543 / 0.506 | 0.748 / 0.580 | 0.754 / 0.595 | - / - | 0.681 / 0.560 |
| DLinear | 0.547 / 0.503 | 0.720 / 0.604 | 0.984 / 0.727 | - / - | 0.750 / 0.611 |
| PatchTST | 0.557 / 0.519 | 0.711 / 0.570 | 0.816 / 0.619 | - / - | 0.694 / 0.569 |
| TimesNet | 0.892 / 0.625 | 0.940 / 0.665 | 0.945 / 0.653 | - / - | 0.925 / 0.647 |
| FEDformer | 0.593 / 0.529 | 0.652 / 0.563 | 0.731 / 0.594 | - / - | 0.658 / 0.562 |
| Autoformer | 0.681 / 0.570 | 0.725 / 0.602 | 0.761 / 0.624 | - / - | 0.722 / 0.598 |
| Stationary | 0.952 / 0.650 | 0.943 / 0.645 | 0.935 / 0.644 | - / - | 0.943 / 0.646 |
| ETSformer | 1.169 / 0.832 | 1.221 / 0.853 | 1.179 / 0.832 | - / - | 1.189 / 0.839 |
| LightTS | 1.483 / 0.91 | 1.525 / 0.93 | 1.347 / 0.87 | - / - | 1.451 / 0.903 |
| Informer | 1.225 / 0.812 | 1.249 / 0.828 | 1.202 / 0.811 | - / - | 1.225 / 0.817 |
| Reformer | 1.198 / 0.795 | 1.273 / 0.853 | 1.254 / 0.857 | - / - | 1.241 / 0.835 |


#### ETTh2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.332 / 0.394 | 0.405 / 0.423 | 0.410 / 0.438 | - / - | 0.382 / 0.418 |
| Time-LLM | 0.336 / 0.397 | 0.406 / 0.425 | 0.405 / 0.432 | - / - | 0.382 / 0.418 |
| GPT4TS | 0.376 / 0.421 | 0.418 / 0.441 | 0.408 / 0.439 | - / - | 0.400 / 0.433 |
| DLinear | 0.442 / 0.456 | 0.617 / 0.542 | 1.424 / 0.849 | - / - | 0.694 / 0.577 |
| PatchTST | 0.401 / 0.421 | 0.452 / 0.455 | 0.464 / 0.469 | - / - | 0.827 / 0.615 |
| TimesNet | 0.409 / 0.420 | 0.483 / 0.464 | 0.499 / 0.479 | - / - | 0.439 / 0.448 |
| FEDformer | 0.390 / 0.424 | 0.457 / 0.465 | 0.477 / 0.483 | - / - | 0.463 / 0.454 |
| Autoformer | 0.428 / 0.468 | 0.496 / 0.504 | 0.486 / 0.496 | - / - | 0.441 / 0.457 |
| Stationary | 0.408 / 0.423 | 0.497 / 0.468 | 0.507 / 0.481 | - / - | 0.470 / 0.489 |
| ETSformer | 0.678 / 0.619 | 0.845 / 0.697 | 0.905 / 0.727 | - / - | 0.809 / 0.681 |
| LightTS | 2.022 / 1.006 | 3.534 / 1.348 | 4.063 / 1.451 | - / - | 3.206 / 1.268 |
| Informer | 3.837 / 1.508 | 3.975 / 1.933 | 3.956 / 1.520 | - / - | 3.922 / 1.653 |
| Reformer | 3.753 / 1.518 | 3.516 / 1.473 | 3.312 / 1.427 | - / - | 3.527 / 1.472 |


#### ETTm1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.313 / 0.369 | 0.438 / 0.427 | 0.446 / 0.431 | 0.485 / 0.478 | 0.421 / 0.426 |
| Time-LLM | 0.316 / 0.377 | 0.450 / 0.464 | 0.450 / 0.424 | 0.483 / 0.471 | 0.425 / 0.434 |
| GPT4TS | 0.386 / 0.405 | 0.440 / 0.438 | 0.485 / 0.459 | 0.577 / 0.499 | 0.472 / 0.450 |
| DLinear | 0.332 / 0.374 | 0.358 / 0.390 | 0.402 / 0.416 | 0.511 / 0.489 | 0.400 / 0.417 |
| PatchTST | 0.399 / 0.414 | 0.441 / 0.436 | 0.499 / 0.467 | 0.767 / 0.587 | 0.526 / 0.476 |
| TimesNet | 0.606 / 0.518 | 0.681 / 0.539 | 0.786 / 0.597 | 0.796 / 0.593 | 0.717 / 0.561 |
| FEDformer | 0.628 / 0.544 | 0.666 / 0.566 | 0.807 / 0.628 | 0.822 / 0.633 | 0.730 / 0.592 |
| Autoformer | 0.726 / 0.578 | 0.750 / 0.591 | 0.851 / 0.659 | 0.857 / 0.655 | 0.796 / 0.620 |
| Stationary | 0.823 / 0.587 | 0.844 / 0.591 | 0.870 / 0.603 | 0.893 / 0.611 | 0.857 / 0.598 |
| ETSformer | 1.031 / 0.747 | 1.087 / 0.766 | 1.138 / 0.787 | 1.245 / 0.831 | 1.125 / 0.782 |
| LightTS | 1.048 / 0.733 | 1.097 / 0.756 | 1.147 / 0.775 | 1.200 / 0.799 | 1.123 / 0.765 |
| Informer | 1.130 / 0.775 | 1.150 / 0.788 | 1.198 / 0.809 | 1.175 / 0.794 | 1.163 / 0.791 |
| Reformer | 1.234 / 0.798 | 1.287 / 0.839 | 1.288 / 0.842 | 1.247 / 0.828 | 1.264 / 0.826 |


#### ETTm2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.176 / 0.260 | 0.213 / 0.286 | 0.271 / 0.327 | 0.436 / 0.415 | 0.274 / 0.322 |
| Time-LLM | 0.174 / 0.261 | 0.215 / 0.287 | 0.273 / 0.330 | 0.433 / 0.412 | 0.274 / 0.323 |
| GPT4TS | 0.199 / 0.280 | 0.256 / 0.316 | 0.318 / 0.353 | 0.460 / 0.436 | 0.308 / 0.346 |
| DLinear | 0.236 / 0.326 | 0.306 / 0.373 | 0.380 / 0.423 | 0.674 / 0.583 | 0.399 / 0.426 |
| PatchTST | 0.206 / 0.288 | 0.264 / 0.324 | 0.334 / 0.367 | 0.454 / 0.432 | 0.314 / 0.352 |
| TimesNet | 0.220 / 0.299 | 0.311 / 0.361 | 0.338 / 0.366 | 0.509 / 0.465 | 0.344 / 0.372 |
| FEDformer | 0.229 / 0.320 | 0.394 / 0.361 | 0.378 / 0.427 | 0.523 / 0.510 | 0.381 / 0.404 |
| Autoformer | 0.232 / 0.322 | 0.291 / 0.357 | 0.478 / 0.517 | 0.553 / 0.538 | 0.388 / 0.433 |
| Stationary | 0.238 / 0.316 | 0.298 / 0.349 | 0.353 / 0.380 | 0.475 / 0.445 | 0.341 / 0.372 |
| ETSformer | 0.404 / 0.485 | 0.479 / 0.521 | 0.552 / 0.555 | 0.701 / 0.627 | 0.534 / 0.547 |
| LightTS | 1.108 / 0.772 | 1.317 / 0.850 | 1.415 / 0.879 | 1.822 / 0.984 | 1.415 / 0.871 |
| Informer | 3.599 / 1.478 | 3.578 / 1.475 | 3.561 / 1.473 | 3.896 / 1.533 | 3.658 / 1.489 |
| Reformer | 3.883 / 1.545 | 3.553 / 1.484 | 3.446 / 1.460 | 3.445 / 1.460 | 3.581 / 1.487 |


#### Weather

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.168 / 0.220 | 0.220 / 0.267 | 0.278 / 0.317 | 0.367 / 0.384 | 0.258 / 0.297 |
| Time-LLM | 0.172 / 0.263 | 0.224 / 0.271 | 0.282 / 0.321 | 0.366 / 0.381 | 0.260 / 0.309 |
| GPT4TS | 0.175 / 0.230 | 0.227 / 0.276 | 0.286 / 0.322 | 0.366 / 0.379 | 0.263 / 0.301 |
| DLinear | 0.184 / 0.242 | 0.228 / 0.283 | 0.279 / 0.322 | 0.364 / 0.388 | 0.263 / 0.308 |
| PatchTST | 0.171 / 0.224 | 0.230 / 0.277 | 0.294 / 0.326 | 0.384 / 0.387 | 0.269 / 0.303 |
| TimesNet | 0.207 / 0.253 | 0.272 / 0.307 | 0.313 / 0.328 | 0.400 / 0.385 | 0.298 / 0.318 |
| FEDformer | 0.229 / 0.309 | 0.265 / 0.317 | 0.353 / 0.392 | 0.391 / 0.394 | 0.309 / 0.353 |
| Autoformer | 0.227 / 0.299 | 0.278 / 0.333 | 0.351 / 0.393 | 0.387 / 0.389 | 0.310 / 0.353 |
| Stationary | 0.215 / 0.252 | 0.290 / 0.307 | 0.353 / 0.348 | 0.452 / 0.407 | 0.327 / 0.328 |
| ETSformer | 0.218 / 0.295 | 0.294 / 0.331 | 0.359 / 0.398 | 0.461 / 0.461 | 0.333 / 0.371 |
| LightTS | 0.230 / 0.285 | 0.274 / 0.323 | 0.318 / 0.355 | 0.401 / 0.418 | 0.305 / 0.345 |
| Informer | 0.497 / 0.497 | 0.620 / 0.545 | 0.649 / 0.547 | 0.570 / 0.522 | 0.584 / 0.527 |
| Reformer | 0.406 / 0.435 | 0.446 / 0.450 | 0.465 / 0.459 | 0.471 / 0.468 | 0.447 / 0.453 |


#### Electricity

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.143 / 0.238 | 0.155 / 0.240 | 0.174 / 0.273 | 0.220 / 0.308 | 0.173 / 0.265 |
| Time-LLM | 0.147 / 0.242 | 0.158 / 0.241 | 0.178 / 0.277 | 0.224 / 0.312 | 0.179 / 0.268 |
| GPT4TS | 0.143 / 0.241 | 0.159 / 0.255 | 0.179 / 0.274 | 0.233 / 0.323 | 0.178 / 0.273 |
| DLinear | 0.150 / 0.251 | 0.163 / 0.263 | 0.175 / 0.278 | 0.219 / 0.311 | 0.176 / 0.275 |
| PatchTST | 0.145 / 0.244 | 0.163 / 0.260 | 0.183 / 0.281 | 0.233 / 0.323 | 0.181 / 0.277 |
| TimesNet | 0.315 / 0.389 | 0.318 / 0.396 | 0.340 / 0.415 | 0.635 / 0.613 | 0.402 / 0.453 |
| FEDformer | 0.235 / 0.322 | 0.247 / 0.341 | 0.267 / 0.356 | 0.318 / 0.394 | 0.266 / 0.353 |
| Autoformer | 0.297 / 0.367 | 0.308 / 0.375 | 0.354 / 0.411 | 0.426 / 0.466 | 0.346 / 0.404 |
| Stationary | 0.484 / 0.518 | 0.501 / 0.531 | 0.574 / 0.578 | 0.952 / 0.786 | 0.627 / 0.603 |
| ETSformer | 0.697 / 0.638 | 0.718 / 0.648 | 0.758 / 0.667 | 1.028 / 0.788 | 0.800 / 0.685 |
| LightTS | 0.639 / 0.609 | 0.772 / 0.678 | 0.901 / 0.745 | 1.200 / 0.871 | 0.878 / 0.725 |
| Informer | 1.265 / 0.919 | 1.298 / 0.939 | 1.302 / 0.942 | 1.259 / 0.919 | 1.281 / 0.929 |
| Reformer | 1.414 / 0.855 | 1.240 / 0.919 | 1.253 / 0.921 | 1.249 / 0.921 | 1.289 / 0.904 |


#### Traffic

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.410 / 0.287 | 0.415 / 0.290 | 0.439 / 0.316 | - / - | 0.421 / 0.298 |
| Time-LLM | 0.414 / 0.291 | 0.419 / 0.291 | 0.437 / 0.314 | - / - | 0.423 / 0.298 |
| GPT4TS | 0.419 / 0.298 | 0.434 / 0.305 | 0.449 / 0.313 | - / - | 0.434 / 0.305 |
| DLinear | 0.427 / 0.304 | 0.447 / 0.315 | 0.478 / 0.333 | - / - | 0.450 / 0.317 |
| PatchTST | 0.404 / 0.286 | 0.412 / 0.294 | 0.439 / 0.310 | - / - | 0.418 / 0.296 |
| TimesNet | 0.854 / 0.492 | 0.894 / 0.517 | 0.853 / 0.471 | - / - | 0.867 / 0.493 |
| FEDformer | 0.670 / 0.421 | 0.653 / 0.405 | 0.707 / 0.445 | - / - | 0.676 / 0.423 |
| Autoformer | 0.795 / 0.481 | 0.837 / 0.503 | 0.867 / 0.523 | - / - | 0.833 / 0.502 |
| Stationary | 1.468 / 0.821 | 1.509 / 0.838 | 1.602 / 0.860 | - / - | 1.526 / 0.839 |
| ETSformer | 1.643 / 0.855 | 1.856 / 0.928 | 2.080 / 0.999 | - / - | 1.859 / 0.927 |
| LightTS | 1.157 / 0.636 | 1.688 / 0.848 | 1.826 / 0.903 | - / - | 1.557 / 0.795 |
| Informer | 1.557 / 0.821 | 1.596 / 0.834 | 1.621 / 0.841 | - / - | 1.591 / 0.832 |
| Reformer | 1.586 / 0.841 | 1.602 / 0.844 | 1.668 / 0.868 | - / - | 1.618 / 0.851 |


#### Source-reported ranking summary

The following footer is transcribed from the original table. See [source notes](source-notes.md) for the counting convention and known source inconsistencies.

| Model | Reported count |
| --- | ---: |
| RDTU | 39 |
| Time-LLM | 10 |
| GPT4TS | 2 |
| DLinear | 8 |
| PatchTST | 6 |
| TimesNet | 0 |
| FEDformer | 2 |
| Autoformer | 0 |
| Stationary | 0 |
| ETSformer | 0 |
| LightTS | 0 |
| Informer | 0 |
| Reformer | 0 |


[Table S14](C-generalization.md#tab-few-shot-forecasting-5per-full) further investigates model robustness under extreme data scarcity by reducing the training data to 5%. Despite the limited information, RDTU maintains a strong lead over baseline methods, achieving the lowest error rates in 39 instances (“1st Count”). In comparison, the closest competitor, Time-LLM, records 10 wins, while DLinear achieves 8. Although certain long-horizon forecasts (e.g., $H=720$) could not be computed for some datasets due to insufficient training samples, RDTU consistently outperforms peer models on the available horizons, demonstrating superior few-shot adaptability.

## Zero-Shot Forecasting

<a id="tab-zero-shot-forecasting"></a>

### Table S15

**Full zero-shot ETT transfer results.** Lower values are better. Cells retain the numerical precision of the manuscript.

Each cell is **MSE / MAE**. `Avg` denotes the source-reported average over horizons. A single `/` or `--` indicates that both metrics are unavailable in the source.

[Download all values (CSV)](../data/zero-shot-forecasting.csv).


#### ETTh1 → ETTh2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.272 / 0.329 | 0.343 / 0.368 | 0.378 / 0.407 | 0.384 / 0.413 | 0.344 / 0.379 |
| Time-LLM | 0.279 / 0.337 | 0.351 / 0.374 | 0.388 / 0.415 | 0.391 / 0.420 | 0.353 / 0.387 |
| LLMTime | 0.510 / 0.576 | 0.523 / 0.586 | 0.640 / 0.637 | 2.296 / 1.034 | 0.992 / 0.708 |
| GPT4TS | 0.335 / 0.374 | 0.412 / 0.417 | 0.441 / 0.444 | 0.438 / 0.452 | 0.406 / 0.422 |
| DLinear | 0.347 / 0.400 | 0.447 / 0.460 | 0.515 / 0.505 | 0.665 / 0.589 | 0.493 / 0.488 |
| PatchTST | 0.304 / 0.350 | 0.386 / 0.400 | 0.414 / 0.428 | 0.419 / 0.443 | 0.380 / 0.405 |
| TimesNet | 0.358 / 0.387 | 0.427 / 0.429 | 0.449 / 0.451 | 0.448 / 0.458 | 0.421 / 0.431 |
| Autoformer | 0.469 / 0.486 | 0.634 / 0.567 | 0.655 / 0.588 | 0.570 / 0.549 | 0.582 / 0.548 |


#### ETTh1 → ETTm2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.178 / 0.282 | 0.231 / 0.307 | 0.287 / 0.359 | 0.367 / 0.383 | 0.266 / 0.333 |
| Time-LLM | 0.189 / 0.293 | 0.237 / 0.312 | 0.291 / 0.365 | 0.372 / 0.390 | 0.273 / 0.340 |
| LLMTime | 0.646 / 0.563 | 0.934 / 0.654 | 1.157 / 0.728 | 4.730 / 1.531 | 1.867 / 0.869 |
| GPT4TS | 0.236 / 0.315 | 0.287 / 0.342 | 0.341 / 0.374 | 0.435 / 0.422 | 0.325 / 0.363 |
| DLinear | 0.255 / 0.357 | 0.338 / 0.413 | 0.425 / 0.465 | 0.640 / 0.573 | 0.415 / 0.452 |
| PatchTST | 0.215 / 0.304 | 0.275 / 0.339 | 0.334 / 0.373 | 0.431 / 0.424 | 0.314 / 0.360 |
| TimesNet | 0.239 / 0.313 | 0.291 / 0.342 | 0.342 / 0.371 | 0.434 / 0.419 | 0.327 / 0.361 |
| Autoformer | 0.352 / 0.432 | 0.413 / 0.460 | 0.465 / 0.489 | 0.599 / 0.551 | 0.457 / 0.483 |


#### ETTh2 → ETTh1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.446 / 0.449 | 0.462 / 0.459 | 0.503 / 0.480 | 0.509 / 0.495 | 0.480 / 0.471 |
| Time-LLM | 0.450 / 0.452 | 0.465 / 0.461 | 0.501 / 0.482 | 0.501 / 0.502 | 0.479 / 0.474 |
| LLMTime | 1.130 / 0.777 | 1.242 / 0.820 | 1.328 / 0.864 | 4.145 / 1.461 | 1.961 / 0.981 |
| GPT4TS | 0.732 / 0.577 | 0.758 / 0.559 | 0.759 / 0.578 | 0.781 / 0.597 | 0.757 / 0.578 |
| DLinear | 0.689 / 0.555 | 0.707 / 0.568 | 0.710 / 0.577 | 0.704 / 0.596 | 0.703 / 0.574 |
| PatchTST | 0.485 / 0.465 | 0.565 / 0.509 | 0.581 / 0.515 | 0.628 / 0.561 | 0.565 / 0.513 |
| TimesNet | 0.848 / 0.601 | 0.860 / 0.610 | 0.867 / 0.626 | 0.887 / 0.648 | 0.865 / 0.621 |
| Autoformer | 0.693 / 0.569 | 0.760 / 0.601 | 0.781 / 0.619 | 0.796 / 0.644 | 0.757 / 0.608 |


#### ETTh2 → ETTm2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.169 / 0.269 | 0.228 / 0.307 | 0.288 / 0.330 | 0.387 / 0.411 | 0.268 / 0.329 |
| Time-LLM | 0.174 / 0.276 | 0.233 / 0.315 | 0.291 / 0.337 | 0.392 / 0.417 | 0.272 / 0.341 |
| LLMTime | 0.646 / 0.563 | 0.934 / 0.654 | 1.157 / 0.728 | 4.730 / 1.531 | 1.867 / 0.869 |
| GPT4TS | 0.253 / 0.329 | 0.293 / 0.346 | 0.347 / 0.376 | 0.446 / 0.429 | 0.335 / 0.370 |
| DLinear | 0.240 / 0.336 | 0.295 / 0.369 | 0.345 / 0.397 | 0.432 / 0.442 | 0.328 / 0.386 |
| PatchTST | 0.226 / 0.309 | 0.289 / 0.345 | 0.348 / 0.379 | 0.439 / 0.427 | 0.325 / 0.365 |
| TimesNet | 0.248 / 0.324 | 0.296 / 0.352 | 0.353 / 0.383 | 0.471 / 0.446 | 0.342 / 0.376 |
| Autoformer | 0.263 / 0.352 | 0.326 / 0.389 | 0.387 / 0.426 | 0.487 / 0.478 | 0.366 / 0.411 |


#### ETTm1 → ETTh2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.319 / 0.363 | 0.383 / 0.406 | 0.401 / 0.428 | 0.407 / 0.433 | 0.378 / 0.408 |
| Time-LLM | 0.321 / 0.369 | 0.389 / 0.410 | 0.408 / 0.433 | 0.406 / 0.436 | 0.381 / 0.412 |
| LLMTime | 0.510 / 0.576 | 0.523 / 0.586 | 0.640 / 0.637 | 2.296 / 1.034 | 0.992 / 0.708 |
| GPT4TS | 0.353 / 0.392 | 0.443 / 0.437 | 0.469 / 0.461 | 0.466 / 0.468 | 0.433 / 0.439 |
| DLinear | 0.365 / 0.415 | 0.454 / 0.462 | 0.496 / 0.494 | 0.541 / 0.529 | 0.464 / 0.475 |
| PatchTST | 0.354 / 0.385 | 0.447 / 0.434 | 0.481 / 0.463 | 0.474 / 0.471 | 0.439 / 0.438 |
| TimesNet | 0.377 / 0.407 | 0.471 / 0.453 | 0.472 / 0.484 | 0.495 / 0.482 | 0.457 / 0.454 |
| Autoformer | 0.435 / 0.470 | 0.495 / 0.489 | 0.470 / 0.472 | 0.480 / 0.485 | 0.470 / 0.479 |


#### ETTm1 → ETTm2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.165 / 0.254 | 0.225 / 0.315 | 0.282 / 0.334 | 0.372 / 0.362 | 0.261 / 0.316 |
| Time-LLM | 0.169 / 0.257 | 0.227 / 0.318 | 0.290 / 0.338 | 0.375 / 0.367 | 0.268 / 0.320 |
| LLMTime | 0.646 / 0.563 | 0.934 / 0.654 | 1.157 / 0.728 | 4.730 / 1.531 | 1.867 / 0.869 |
| GPT4TS | 0.217 / 0.294 | 0.277 / 0.327 | 0.331 / 0.360 | 0.429 / 0.413 | 0.313 / 0.348 |
| DLinear | 0.221 / 0.314 | 0.286 / 0.359 | 0.357 / 0.406 | 0.476 / 0.476 | 0.335 / 0.389 |
| PatchTST | 0.195 / 0.271 | 0.258 / 0.311 | 0.317 / 0.348 | 0.416 / 0.404 | 0.296 / 0.334 |
| TimesNet | 0.222 / 0.295 | 0.288 / 0.337 | 0.341 / 0.367 | 0.436 / 0.418 | 0.322 / 0.354 |
| Autoformer | 0.385 / 0.457 | 0.433 / 0.469 | 0.476 / 0.477 | 0.582 / 0.535 | 0.469 / 0.484 |


#### ETTm2 → ETTh2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.295 / 0.351 | 0.356 / 0.392 | 0.363 / 0.407 | 0.388 / 0.429 | 0.351 / 0.395 |
| Time-LLM | 0.298 / 0.356 | 0.359 / 0.397 | 0.367 / 0.412 | 0.393 / 0.434 | 0.354 / 0.400 |
| LLMTime | 0.510 / 0.576 | 0.523 / 0.586 | 0.640 / 0.637 | 2.296 / 1.034 | 0.992 / 0.708 |
| GPT4TS | 0.360 / 0.401 | 0.434 / 0.437 | 0.460 / 0.459 | 0.485 / 0.477 | 0.435 / 0.443 |
| DLinear | 0.333 / 0.391 | 0.441 / 0.456 | 0.505 / 0.503 | 0.543 / 0.534 | 0.455 / 0.471 |
| PatchTST | 0.327 / 0.367 | 0.411 / 0.418 | 0.439 / 0.447 | 0.459 / 0.470 | 0.409 / 0.425 |
| TimesNet | 0.360 / 0.401 | 0.434 / 0.437 | 0.460 / 0.459 | 0.485 / 0.477 | 0.435 / 0.443 |
| Autoformer | 0.353 / 0.393 | 0.432 / 0.437 | 0.452 / 0.459 | 0.453 / 0.467 | 0.423 / 0.439 |


#### ETTm2 → ETTm1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.356 / 0.394 | 0.386 / 0.414 | 0.419 / 0.440 | 0.485 / 0.487 | 0.412 / 0.434 |
| Time-LLM | 0.359 / 0.397 | 0.390 / 0.420 | 0.421 / 0.445 | 0.487 / 0.488 | 0.414 / 0.438 |
| LLMTime | 1.179 / 0.781 | 1.327 / 0.846 | 1.478 / 0.902 | 3.749 / 1.408 | 1.933 / 0.984 |
| GPT4TS | 0.747 / 0.558 | 0.781 / 0.560 | 0.778 / 0.578 | 0.769 / 0.573 | 0.769 / 0.567 |
| DLinear | 0.570 / 0.490 | 0.590 / 0.506 | 0.706 / 0.567 | 0.731 / 0.584 | 0.649 / 0.537 |
| PatchTST | 0.491 / 0.437 | 0.530 / 0.470 | 0.565 / 0.497 | 0.686 / 0.565 | 0.568 / 0.492 |
| TimesNet | 0.747 / 0.558 | 0.781 / 0.560 | 0.778 / 0.578 | 0.769 / 0.573 | 0.769 / 0.567 |
| Autoformer | 0.735 / 0.576 | 0.753 / 0.586 | 0.750 / 0.593 | 0.782 / 0.609 | 0.755 / 0.591 |


[Table S15](C-generalization.md#tab-zero-shot-forecasting) presents the zero-shot learning results on ETT datasets, evaluating the transferability of models between different domains (e.g., $ETTh1 \to ETTh2$). RDTU demonstrates exceptional cross-domain generalization, achieving the best performance (highlighted in red) across the vast majority of transfer scenarios and horizons. While Time-LLM frequently secures the second-best position (blue) and PatchTST consistently ranks third (green), RDTU significantly outperforms both, particularly in challenging transfer tasks such as $ETTm1 \to ETTh2$ and $ETTm2 \to ETTh1$, validating the efficacy of its language-based representations for zero-shot forecasting.

## Zero-shot Length Generalization

<a id="sec-length_generalization"></a>

<a id="tab-length_generalization"></a>

### Table S16

Zero-shot length generalization of RDTU. Models trained only up to $H=336$ under the 5% data regime are directly evaluated on $H=720$ without additional training, and are compared with RDTU trained on $H=720$ using 10% data.

| Dataset | Metric | RDTU Trained on H=336 w/ 5% Data, Eval on H=720 | RDTU Trained on H=720 w/ 10% Data |
| --- | ---: | ---: | ---: |
| ETTh1 | MSE / MAE | 0.705 / 0.598 | 0.694 / 0.587 |
| ETTh2 | MSE / MAE | 0.442 / 0.456 | 0.425 / 0.443 |
| Traffic | MSE / MAE | 0.478 / 0.337 | 0.463 / 0.325 |

[Download table (CSV)](../data/length_generalization.csv).


A core advantage of RDTU is its zero-shot length generalization ability. Unlike conventional forecasting models whose output heads are often tied to a fixed prediction horizon, RDTU formulates forecasting as an autoregressive token generation task. This formulation naturally relaxes fixed output-dimensional constraints and allows the model to generate longer horizons at inference time without modifying the architecture or conducting additional horizon-specific training.

As shown in [Table S16](C-generalization.md#tab-length_generalization), RDTU trained only up to $H=336$ under the 5% data regime can be directly evaluated on $H=720$. Although a moderate performance gap is expected due to longer-horizon error accumulation, the extrapolated model remains highly competitive compared with the model trained directly on $H=720$ using 10% data. For example, on ETTh1, the zero-shot length extrapolation setting obtains 0.705 MSE and 0.598 MAE, which is close to the 0.694 MSE and 0.587 MAE achieved by the stronger 10% $H=720$ training setting. Similar trends are observed on ETTh2 and Traffic, where the performance degradation remains small despite the absence of any $H=720$ training samples. These results demonstrate that RDTU does not merely memorize a fixed output length, but learns a flexible generation policy that can extrapolate to unseen prediction horizons.

<a id="tab-cross_domain_zero_shot"></a>

### Table S17

Cross-domain zero-shot generalization results. All zero-shot models are trained on ETTh1 and directly evaluated on target datasets from different domains without target-domain training. Lower MSE and MAE indicate better performance.

| Target Dataset | Metric | Supervised RDTU | Zero-Shot RDTU | Zero-Shot Time-LLM | Zero-Shot GPT4TS |
| --- | ---: | ---: | ---: | ---: | ---: |
| Electricity | MSE / MAE | 0.156 / 0.246 | 0.182 / 0.270 | 0.254 / 0.312 | 0.328 / 0.385 |
| Weather | MSE / MAE | 0.221 / 0.251 | 0.245 / 0.278 | 0.386 / 0.395 | 0.462 / 0.431 |
| Traffic | MSE / MAE | 0.389 / 0.255 | 0.421 / 0.295 | 0.652 / 0.415 | 0.735 / 0.484 |
| Illness | MSE / MAE | 1.559 / 0.812 | 1.645 / 0.910 | 2.642 / 1.753 | 3.215 / 2.058 |

[Download table (CSV)](../data/cross_domain_zero_shot.csv).


## Cross-Domain Zero-Shot Generalization

<a id="sec-cross_domain_zero_shot"></a>

To further verify whether RDTU learns transferable temporal dynamics rather than relying on dataset-specific tuning, we conduct a more challenging cross-domain zero-shot experiment. Different from the ETT-family transfer setting in [Table S4](04-experiments.md#tab-zero-shot-forecasting-brief), this experiment trains the model only on ETTh1 and directly evaluates it on target datasets from substantially different domains, including Electricity, Weather, Traffic, and Illness.

As shown in [Table S17](C-generalization.md#tab-cross_domain_zero_shot), Zero-Shot RDTU consistently outperforms zero-shot Time-LLM and GPT4TS across all target datasets. For example, on Electricity, RDTU achieves 0.182 MSE and 0.270 MAE, substantially better than Time-LLM with 0.254 MSE and 0.312 MAE. On more heterogeneous domains such as Traffic and Illness, the advantage becomes even more pronounced, indicating that RDTU maintains robust forecasting ability under severe distribution shifts. Moreover, Zero-Shot RDTU remains close to the supervised RDTU upper bound, despite using no target-domain training data. These results provide stronger evidence that the proposed direct temporal unification and reinforcement-driven refinement help the model capture intrinsic and transferable time-series patterns, rather than merely fitting dataset-specific statistics or hyperparameters.

---
Source: full manuscript Appendix C. See the [coverage map](coverage.md) and [source notes](source-notes.md).
