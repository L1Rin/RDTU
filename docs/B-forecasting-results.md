[Home](../README.md) · [Reading guide](index.md) · [Complete PDF](../supplement/RDTU-Supplementary.pdf)

# Full long-term and M4 results

<a id="appx-long-short-term"></a>

## Long-term Forecasting

By leveraging two-stage RDTU framework while bypassing pre-alignment, our method attains SOTA performance in **35** instances across eight time series benchmarks. This underscores the considerable potential of LLMs as robust and reliable time series forecasters.

[Table S10](B-forecasting-results.md#tab-long-term-forecasting-full) presents a comprehensive evaluation of long-term forecasting performance across eight benchmark datasets, categorizing baseline models by their input modality (Language, Multi-Modal, Visual, and Numerical).

<a id="tab-long-term-forecasting-full"></a>

### Table S10

**Full long-term forecasting results.** Lower values are better. Cells retain the numerical precision of the manuscript.

Each cell is **MSE / MAE**. `Avg` denotes the source-reported average over horizons. A single `/` or `--` indicates that both metrics are unavailable in the source.

[Download all values (CSV)](../data/long-term-forecasting-full-new.csv).


#### ETTh1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.351 / 0.382 | 0.389 / 0.403 | 0.412 / 0.419 | 0.442 / 0.446 | 0.399 / 0.413 |
| GPT4TS | 0.370 / 0.389 | 0.412 / 0.413 | 0.448 / 0.431 | 0.441 / 0.449 | 0.418 / 0.421 |
| Time-LLM | 0.376 / 0.402 | 0.407 / 0.421 | 0.430 / 0.438 | 0.457 / 0.468 | 0.418 / 0.432 |
| DMMV-A | 0.354 / 0.389 | 0.393 / 0.405 | 0.387 / 0.413 | 0.445 / 0.450 | 0.395 / 0.414 |
| Time-VLM | 0.361 / 0.386 | 0.397 / 0.415 | 0.420 / 0.421 | 0.441 / 0.458 | 0.405 / 0.420 |
| VisionTS | 0.355 / 0.386 | 0.395 / 0.407 | 0.419 / 0.421 | 0.458 / 0.460 | 0.407 / 0.419 |
| PatchTST | 0.370 / 0.399 | 0.413 / 0.421 | 0.422 / 0.436 | 0.447 / 0.466 | 0.413 / 0.431 |
| CycleNet | 0.374 / 0.396 | 0.406 / 0.415 | 0.431 / 0.430 | 0.450 / 0.464 | 0.415 / 0.426 |
| TimesNet | 0.384 / 0.402 | 0.436 / 0.429 | 0.491 / 0.469 | 0.521 / 0.500 | 0.458 / 0.450 |
| DLinear | 0.375 / 0.399 | 0.405 / 0.416 | 0.439 / 0.416 | 0.472 / 0.490 | 0.423 / 0.430 |
| FEDformer | 0.376 / 0.419 | 0.420 / 0.448 | 0.459 / 0.465 | 0.506 / 0.507 | 0.440 / 0.460 |


#### ETTh2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.263 / 0.329 | 0.334 / 0.372 | 0.355 / 0.381 | 0.395 / 0.425 | 0.337 / 0.377 |
| GPT4TS | 0.280 / 0.335 | 0.348 / 0.380 | 0.380 / 0.405 | 0.406 / 0.436 | 0.354 / 0.389 |
| Time-LLM | 0.286 / 0.346 | 0.361 / 0.391 | 0.390 / 0.414 | 0.405 / 0.434 | 0.361 / 0.396 |
| DMMV-A | 0.294 / 0.349 | 0.339 / 0.395 | 0.322 / 0.384 | 0.392 / 0.425 | 0.337 / 0.388 |
| Time-VLM | 0.267 / 0.335 | 0.326 / 0.373 | 0.357 / 0.406 | 0.412 / 0.449 | 0.341 / 0.391 |
| VisionTS | 0.288 / 0.334 | 0.349 / 0.380 | 0.364 / 0.398 | 0.403 / 0.431 | 0.351 / 0.386 |
| PatchTST | 0.274 / 0.336 | 0.339 / 0.379 | 0.329 / 0.380 | 0.379 / 0.422 | 0.330 / 0.379 |
| CycleNet | 0.279 / 0.341 | 0.342 / 0.385 | 0.371 / 0.413 | 0.426 / 0.451 | 0.355 / 0.398 |
| TimesNet | 0.340 / 0.374 | 0.402 / 0.414 | 0.452 / 0.452 | 0.462 / 0.468 | 0.414 / 0.427 |
| DLinear | 0.289 / 0.353 | 0.383 / 0.418 | 0.448 / 0.465 | 0.605 / 0.551 | 0.431 / 0.447 |
| FEDformer | 0.358 / 0.397 | 0.429 / 0.439 | 0.496 / 0.487 | 0.463 / 0.474 | 0.437 / 0.449 |


#### ETTm1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.272 / 0.326 | 0.327 / 0.354 | 0.350 / 0.375 | 0.410 / 0.412 | 0.340 / 0.367 |
| GPT4TS | 0.300 / 0.340 | 0.343 / 0.368 | 0.376 / 0.386 | 0.431 / 0.416 | 0.363 / 0.378 |
| Time-LLM | 0.291 / 0.341 | 0.341 / 0.369 | 0.359 / 0.379 | 0.433 / 0.419 | 0.356 / 0.377 |
| DMMV-A | 0.279 / 0.329 | 0.317 / 0.357 | 0.351 / 0.381 | 0.411 / 0.415 | 0.340 / 0.371 |
| Time-VLM | 0.304 / 0.346 | 0.332 / 0.366 | 0.364 / 0.383 | 0.402 / 0.410 | 0.351 / 0.376 |
| VisionTS | 0.284 / 0.332 | 0.327 / 0.362 | 0.354 / 0.382 | 0.411 / 0.415 | 0.344 / 0.373 |
| PatchTST | 0.290 / 0.342 | 0.332 / 0.369 | 0.366 / 0.392 | 0.416 / 0.420 | 0.351 / 0.381 |
| CycleNet | 0.299 / 0.348 | 0.334 / 0.367 | 0.368 / 0.386 | 0.417 / 0.414 | 0.355 / 0.379 |
| TimesNet | 0.338 / 0.375 | 0.374 / 0.387 | 0.410 / 0.411 | 0.478 / 0.450 | 0.400 / 0.406 |
| DLinear | 0.299 / 0.343 | 0.335 / 0.365 | 0.369 / 0.386 | 0.425 / 0.421 | 0.357 / 0.379 |
| FEDformer | 0.379 / 0.419 | 0.426 / 0.441 | 0.445 / 0.459 | 0.543 / 0.490 | 0.448 / 0.452 |


#### ETTm2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.157 / 0.244 | 0.219 / 0.288 | 0.270 / 0.323 | 0.354 / 0.379 | 0.250 / 0.309 |
| GPT4TS | 0.163 / 0.249 | 0.222 / 0.291 | 0.273 / 0.327 | 0.357 / 0.376 | 0.254 / 0.311 |
| Time-LLM | 0.162 / 0.248 | 0.235 / 0.304 | 0.280 / 0.329 | 0.366 / 0.382 | 0.261 / 0.316 |
| DMMV-A | 0.172 / 0.260 | 0.227 / 0.298 | 0.272 / 0.327 | 0.351 / 0.381 | 0.256 / 0.317 |
| Time-VLM | 0.160 / 0.250 | 0.215 / 0.291 | 0.270 / 0.325 | 0.348 / 0.378 | 0.248 / 0.311 |
| VisionTS | 0.174 / 0.262 | 0.228 / 0.297 | 0.281 / 0.337 | 0.384 / 0.410 | 0.267 / 0.327 |
| PatchTST | 0.165 / 0.255 | 0.220 / 0.292 | 0.274 / 0.329 | 0.362 / 0.385 | 0.255 / 0.315 |
| CycleNet | 0.159 / 0.247 | 0.214 / 0.286 | 0.269 / 0.322 | 0.363 / 0.382 | 0.251 / 0.309 |
| TimesNet | 0.187 / 0.267 | 0.249 / 0.309 | 0.321 / 0.351 | 0.408 / 0.403 | 0.291 / 0.333 |
| DLinear | 0.167 / 0.260 | 0.224 / 0.303 | 0.281 / 0.342 | 0.397 / 0.421 | 0.267 / 0.332 |
| FEDformer | 0.203 / 0.287 | 0.269 / 0.328 | 0.325 / 0.366 | 0.421 / 0.415 | 0.305 / 0.349 |


#### Illness

| Model | 24 | 36 | 48 | 60 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 1.609 / 0.771 | 1.453 / 0.835 | 1.545 / 0.841 | 1.630 / 0.802 | 1.559 / 0.812 |
| GPT4TS | 1.869 / 0.823 | 1.853 / 0.854 | 1.886 / 0.855 | 1.877 / 0.877 | 1.871 / 0.852 |
| Time-LLM | 1.792 / 0.807 | 1.833 / 0.833 | 2.269 / 1.012 | 2.177 / 0.925 | 2.018 / 0.894 |
| DMMV-A | 1.409 / 0.754 | 1.290 / 0.745 | 1.499 / 0.810 | 1.428 / 0.773 | 1.407 / 0.771 |
| Time-VLM | -- | -- | -- | -- | -- |
| VisionTS | 1.613 / 0.834 | 1.316 / 0.750 | 1.548 / 0.818 | 1.450 / 0.783 | 1.482 / 0.796 |
| PatchTST | 1.319 / 0.754 | 1.430 / 0.834 | 1.553 / 0.815 | 1.470 / 0.788 | 1.443 / 0.798 |
| CycleNet | 2.255 / 1.017 | 2.121 / 0.950 | 2.187 / 1.007 | 2.185 / 0.997 | 2.187 / 0.992 |
| TimesNet | 2.317 / 0.934 | 1.972 / 0.920 | 2.238 / 0.940 | 2.027 / 0.928 | 2.139 / 0.931 |
| DLinear | 2.215 / 1.081 | 1.963 / 0.963 | 2.130 / 1.024 | 2.368 / 1.096 | 2.169 / 1.041 |
| FEDformer | 3.228 / 1.260 | 2.679 / 1.080 | 2.622 / 1.078 | 2.857 / 1.157 | 2.847 / 1.144 |


#### Electricity

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.124 / 0.210 | 0.144 / 0.235 | 0.162 / 0.257 | 0.193 / 0.281 | 0.156 / 0.246 |
| GPT4TS | 0.141 / 0.239 | 0.158 / 0.253 | 0.172 / 0.266 | 0.207 / 0.293 | 0.170 / 0.263 |
| Time-LLM | 0.137 / 0.233 | 0.152 / 0.247 | 0.169 / 0.267 | 0.200 / 0.290 | 0.165 / 0.259 |
| DMMV-A | 0.126 / 0.213 | 0.145 / 0.237 | 0.162 / 0.254 | 0.197 / 0.286 | 0.158 / 0.248 |
| Time-VLM | 0.142 / 0.245 | 0.157 / 0.260 | 0.174 / 0.276 | 0.214 / 0.308 | 0.172 / 0.272 |
| VisionTS | 0.127 / 0.217 | 0.148 / 0.237 | 0.163 / 0.253 | 0.199 / 0.293 | 0.159 / 0.250 |
| PatchTST | 0.129 / 0.222 | 0.157 / 0.240 | 0.163 / 0.259 | 0.197 / 0.290 | 0.162 / 0.253 |
| CycleNet | 0.128 / 0.223 | 0.144 / 0.237 | 0.160 / 0.254 | 0.198 / 0.287 | 0.158 / 0.250 |
| TimesNet | 0.168 / 0.272 | 0.184 / 0.289 | 0.198 / 0.300 | 0.220 / 0.320 | 0.193 / 0.295 |
| DLinear | 0.140 / 0.237 | 0.153 / 0.249 | 0.169 / 0.267 | 0.203 / 0.301 | 0.166 / 0.264 |
| FEDformer | 0.193 / 0.308 | 0.201 / 0.315 | 0.214 / 0.329 | 0.246 / 0.355 | 0.214 / 0.327 |


#### Weather

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.141 / 0.184 | 0.189 / 0.227 | 0.239 / 0.272 | 0.314 / 0.322 | 0.221 / 0.251 |
| GPT4TS | 0.148 / 0.188 | 0.192 / 0.230 | 0.246 / 0.273 | 0.320 / 0.328 | 0.227 / 0.255 |
| Time-LLM | 0.155 / 0.199 | 0.223 / 0.261 | 0.251 / 0.279 | 0.345 / 0.342 | 0.244 / 0.270 |
| DMMV-A | 0.143 / 0.195 | 0.187 / 0.242 | 0.237 / 0.273 | 0.302 / 0.315 | 0.217 / 0.256 |
| Time-VLM | 0.148 / 0.200 | 0.193 / 0.240 | 0.243 / 0.281 | 0.312 / 0.332 | 0.224 / 0.263 |
| VisionTS | 0.146 / 0.191 | 0.194 / 0.238 | 0.243 / 0.275 | 0.318 / 0.328 | 0.225 / 0.258 |
| PatchTST | 0.149 / 0.198 | 0.194 / 0.241 | 0.245 / 0.282 | 0.314 / 0.334 | 0.226 / 0.264 |
| CycleNet | 0.167 / 0.221 | 0.212 / 0.258 | 0.260 / 0.293 | 0.328 / 0.339 | 0.242 / 0.278 |
| TimesNet | 0.172 / 0.220 | 0.219 / 0.261 | 0.280 / 0.306 | 0.365 / 0.359 | 0.259 / 0.287 |
| DLinear | 0.176 / 0.237 | 0.220 / 0.282 | 0.265 / 0.319 | 0.333 / 0.362 | 0.249 / 0.300 |
| FEDformer | 0.217 / 0.296 | 0.276 / 0.336 | 0.339 / 0.380 | 0.403 / 0.428 | 0.309 / 0.360 |


#### Traffic

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.358 / 0.235 | 0.375 / 0.248 | 0.388 / 0.256 | 0.435 / 0.280 | 0.389 / 0.255 |
| GPT4TS | 0.396 / 0.264 | 0.412 / 0.268 | 0.421 / 0.273 | 0.455 / 0.291 | 0.421 / 0.274 |
| Time-LLM | 0.392 / 0.267 | 0.409 / 0.271 | 0.434 / 0.296 | 0.451 / 0.291 | 0.422 / 0.281 |
| DMMV-A | 0.344 / 0.237 | 0.363 / 0.249 | 0.387 / 0.256 | 0.433 / 0.284 | 0.389 / 0.257 |
| Time-VLM | 0.393 / 0.290 | 0.405 / 0.296 | 0.420 / 0.305 | 0.459 / 0.323 | 0.419 / 0.304 |
| VisionTS | 0.346 / 0.232 | 0.376 / 0.245 | 0.389 / 0.252 | 0.432 / 0.293 | 0.386 / 0.256 |
| PatchTST | 0.360 / 0.249 | 0.379 / 0.256 | 0.392 / 0.264 | 0.432 / 0.286 | 0.391 / 0.264 |
| CycleNet | 0.397 / 0.278 | 0.411 / 0.283 | 0.424 / 0.289 | 0.450 / 0.305 | 0.421 / 0.289 |
| TimesNet | 0.593 / 0.321 | 0.617 / 0.336 | 0.629 / 0.336 | 0.640 / 0.350 | 0.620 / 0.336 |
| DLinear | 0.410 / 0.282 | 0.423 / 0.287 | 0.436 / 0.296 | 0.466 / 0.315 | 0.434 / 0.295 |
| FEDformer | 0.587 / 0.366 | 0.604 / 0.373 | 0.621 / 0.383 | 0.626 / 0.382 | 0.610 / 0.376 |


#### Source-reported ranking summary

The following footer is transcribed from the original table. See [source notes](source-notes.md) for the counting convention and known source inconsistencies.

| Model | Reported count |
| --- | ---: |
| RDTU | 35 |
| GPT4TS | 2 |
| Time-LLM | 0 |
| DMMV-A | 23 |
| Time-VLM | 6 |
| VisionTS | 6 |
| PatchTST | 7 |
| CycleNet | 6 |
| TimesNet | 0 |
| DLinear | 0 |
| FEDformer | 0 |


<a id="tab-long-term-forecasting-additional"></a>

### Table S11

**Long-term forecasting: additional baselines.** Lower values are better. Cells retain the numerical precision of the manuscript.

Each cell is **MSE / MAE**. `Avg` denotes the source-reported average over horizons. A single `/` or `--` indicates that both metrics are unavailable in the source.

[Download all values (CSV)](../data/long-term-forecasting-additional.csv).


#### ETTh1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.351 / 0.382 | 0.389 / 0.403 | 0.412 / 0.419 | 0.442 / 0.446 | 0.399 / 0.413 |
| Autoformer | 0.449 / 0.459 | 0.500 / 0.482 | 0.521 / 0.496 | 0.514 / 0.512 | 0.496 / 0.487 |
| Stationary | 0.513 / 0.491 | 0.534 / 0.504 | 0.588 / 0.535 | 0.643 / 0.616 | 0.570 / 0.537 |
| ETSformer | 0.494 / 0.479 | 0.538 / 0.504 | 0.574 / 0.521 | 0.562 / 0.535 | 0.542 / 0.510 |
| LightTS | 0.424 / 0.432 | 0.475 / 0.462 | 0.518 / 0.488 | 0.547 / 0.533 | 0.491 / 0.479 |
| Informer | 0.865 / 0.713 | 1.008 / 0.792 | 1.107 / 0.809 | 1.181 / 0.865 | 1.040 / 0.795 |
| Reformer | 0.837 / 0.728 | 0.923 / 0.766 | 1.097 / 0.835 | 1.257 / 0.889 | 1.029 / 0.805 |


#### ETTh2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.263 / 0.329 | 0.334 / 0.372 | 0.355 / 0.381 | 0.395 / 0.425 | 0.337 / 0.377 |
| Autoformer | 0.346 / 0.388 | 0.456 / 0.452 | 0.482 / 0.486 | 0.515 / 0.511 | 0.450 / 0.459 |
| Stationary | 0.476 / 0.458 | 0.512 / 0.493 | 0.552 / 0.551 | 0.562 / 0.560 | 0.526 / 0.516 |
| ETSformer | 0.340 / 0.391 | 0.430 / 0.439 | 0.485 / 0.479 | 0.500 / 0.497 | 0.439 / 0.452 |
| LightTS | 0.397 / 0.437 | 0.520 / 0.504 | 0.626 / 0.559 | 0.863 / 0.672 | 0.602 / 0.543 |
| Informer | 3.755 / 1.525 | 5.602 / 1.931 | 4.721 / 1.835 | 3.647 / 1.625 | 4.431 / 1.729 |
| Reformer | 2.626 / 1.317 | 11.12 / 2.979 | 9.323 / 2.769 | 3.874 / 1.697 | 6.736 / 2.191 |


#### ETTm1

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.272 / 0.326 | 0.327 / 0.354 | 0.350 / 0.375 | 0.410 / 0.412 | 0.340 / 0.367 |
| Autoformer | 0.505 / 0.475 | 0.553 / 0.496 | 0.621 / 0.537 | 0.671 / 0.561 | 0.588 / 0.517 |
| Stationary | 0.386 / 0.398 | 0.459 / 0.444 | 0.495 / 0.464 | 0.585 / 0.516 | 0.481 / 0.456 |
| ETSformer | 0.375 / 0.398 | 0.408 / 0.410 | 0.435 / 0.428 | 0.499 / 0.462 | 0.429 / 0.425 |
| LightTS | 0.374 / 0.400 | 0.400 / 0.407 | 0.438 / 0.438 | 0.527 / 0.502 | 0.435 / 0.437 |
| Informer | 0.672 / 0.571 | 0.795 / 0.669 | 1.212 / 0.871 | 1.166 / 0.823 | 0.961 / 0.734 |
| Reformer | 0.538 / 0.528 | 0.658 / 0.592 | 0.898 / 0.721 | 1.102 / 0.841 | 0.799 / 0.671 |


#### ETTm2

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.157 / 0.244 | 0.219 / 0.288 | 0.270 / 0.323 | 0.354 / 0.379 | 0.250 / 0.309 |
| Autoformer | 0.255 / 0.339 | 0.281 / 0.340 | 0.339 / 0.372 | 0.433 / 0.432 | 0.327 / 0.371 |
| Stationary | 0.192 / 0.274 | 0.280 / 0.339 | 0.334 / 0.361 | 0.417 / 0.413 | 0.306 / 0.347 |
| ETSformer | 0.189 / 0.280 | 0.253 / 0.319 | 0.314 / 0.357 | 0.414 / 0.413 | 0.293 / 0.342 |
| LightTS | 0.209 / 0.308 | 0.311 / 0.382 | 0.442 / 0.466 | 0.675 / 0.587 | 0.409 / 0.436 |
| Informer | 0.365 / 0.453 | 0.533 / 0.563 | 1.363 / 0.887 | 3.379 / 1.338 | 1.410 / 0.810 |
| Reformer | 0.658 / 0.619 | 1.078 / 0.827 | 1.549 / 0.972 | 2.631 / 1.242 | 1.479 / 0.915 |


#### Weather

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.141 / 0.184 | 0.189 / 0.227 | 0.239 / 0.272 | 0.314 / 0.322 | 0.221 / 0.251 |
| Autoformer | 0.266 / 0.336 | 0.307 / 0.367 | 0.359 / 0.395 | 0.419 / 0.428 | 0.338 / 0.382 |
| Stationary | 0.173 / 0.223 | 0.245 / 0.285 | 0.321 / 0.338 | 0.414 / 0.410 | 0.288 / 0.314 |
| ETSformer | 0.197 / 0.281 | 0.237 / 0.312 | 0.298 / 0.353 | 0.352 / 0.288 | 0.271 / 0.334 |
| LightTS | 0.182 / 0.242 | 0.227 / 0.287 | 0.282 / 0.334 | 0.352 / 0.386 | 0.261 / 0.312 |
| Informer | 0.300 / 0.384 | 0.598 / 0.544 | 0.578 / 0.523 | 1.059 / 0.741 | 0.634 / 0.548 |
| Reformer | 0.689 / 0.596 | 0.752 / 0.638 | 0.639 / 0.596 | 1.130 / 0.792 | 0.803 / 0.656 |


#### Electricity

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.124 / 0.210 | 0.144 / 0.235 | 0.162 / 0.257 | 0.193 / 0.281 | 0.156 / 0.246 |
| Autoformer | 0.201 / 0.317 | 0.222 / 0.334 | 0.231 / 0.338 | 0.254 / 0.361 | 0.227 / 0.338 |
| Stationary | 0.169 / 0.273 | 0.182 / 0.286 | 0.200 / 0.304 | 0.222 / 0.321 | 0.193 / 0.296 |
| ETSformer | 0.187 / 0.304 | 0.199 / 0.315 | 0.212 / 0.329 | 0.233 / 0.345 | 0.208 / 0.323 |
| LightTS | 0.207 / 0.307 | 0.213 / 0.316 | 0.230 / 0.333 | 0.265 / 0.360 | 0.229 / 0.329 |
| Informer | 0.274 / 0.368 | 0.296 / 0.386 | 0.300 / 0.394 | 0.373 / 0.439 | 0.311 / 0.397 |
| Reformer | 0.312 / 0.402 | 0.348 / 0.433 | 0.350 / 0.433 | 0.340 / 0.420 | 0.338 / 0.422 |


#### Traffic

| Model | 96 | 192 | 336 | 720 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 0.358 / 0.235 | 0.375 / 0.248 | 0.388 / 0.256 | 0.435 / 0.280 | 0.389 / 0.255 |
| Autoformer | 0.613 / 0.388 | 0.616 / 0.382 | 0.622 / 0.337 | 0.660 / 0.408 | 0.628 / 0.379 |
| Stationary | 0.612 / 0.338 | 0.613 / 0.340 | 0.618 / 0.328 | 0.653 / 0.355 | 0.624 / 0.340 |
| ETSformer | 0.607 / 0.392 | 0.621 / 0.399 | 0.622 / 0.396 | 0.632 / 0.396 | 0.621 / 0.396 |
| LightTS | 0.615 / 0.391 | 0.601 / 0.382 | 0.613 / 0.386 | 0.658 / 0.407 | 0.622 / 0.392 |
| Informer | 0.719 / 0.391 | 0.696 / 0.379 | 0.777 / 0.420 | 0.864 / 0.472 | 0.764 / 0.416 |
| Reformer | 0.732 / 0.423 | 0.733 / 0.420 | 0.742 / 0.420 | 0.755 / 0.423 | 0.741 / 0.422 |


#### ILI

| Model | 24 | 36 | 48 | 60 | Avg |
| --- | ---: | ---: | ---: | ---: | ---: |
| **RDTU** | 1.609 / 0.771 | 1.453 / 0.835 | 1.545 / 0.841 | 1.630 / 0.802 | 1.559 / 0.812 |
| Autoformer | 3.483 / 1.287 | 3.103 / 1.148 | 2.669 / 1.085 | 2.770 / 1.125 | 3.006 / 1.161 |
| Stationary | 2.294 / 0.945 | 1.825 / 0.848 | 2.010 / 0.900 | 2.178 / 0.963 | 2.077 / 0.914 |
| ETSformer | 2.527 / 1.020 | 2.615 / 1.007 | 2.359 / 0.972 | 2.487 / 1.016 | 2.497 / 1.004 |
| LightTS | 8.313 / 2.144 | 6.631 / 1.902 | 7.299 / 1.982 | 7.283 / 1.985 | 7.382 / 2.003 |
| Informer | 5.764 / 1.677 | 4.755 / 1.467 | 4.763 / 1.469 | 5.264 / 1.564 | 5.137 / 1.544 |
| Reformer | 4.400 / 1.382 | 4.783 / 1.448 | 4.832 / 1.465 | 4.882 / 1.483 | 4.724 / 1.445 |


#### Source-reported ranking summary

The following footer is transcribed from the original table. See [source notes](source-notes.md) for the counting convention and known source inconsistencies.

| Model | Reported count |
| --- | ---: |
| RDTU | 40 |
| Autoformer | 0 |
| Stationary | 0 |
| ETSformer | 0 |
| LightTS | 0 |
| Informer | 0 |
| Reformer | 0 |


[Table S11](B-forecasting-results.md#tab-long-term-forecasting-additional) presents an extensive evaluation of the proposed RDTU method against six state-of-the-art baseline models (Autoformer, Stationary, ETSformer, LightTS, Informer, and Reformer) across eight benchmark datasets. The experimental results clearly demonstrate the superior performance of RDTU for long-term time series forecasting.

As indicated by the bold red values, RDTU achieves the lowest Mean Squared Error (MSE) across the listed settings and the lowest Mean Absolute Error (MAE) in all but one individual horizon setting ($`H \in \{24, 36, 48, 60\}`$ for ILI and $`H \in \{96, 192, 336, 720\}`$ for other datasets). The quantitative summary at the bottom of the table confirms this dominance, with a source-reported "1st Count" of 40 for RDTU and 0 for each listed baseline. This count is retained as reported; it is distinct from the number of individual MSE and MAE cells in the table. While models such as LightTS and ETSformer occasionally yield the second-best results (highlighted in blue), RDTU consistently provides significant accuracy improvements.

## Short-term Forecasting

Our complete results on short-term forecasting are presented in [Table S12](B-forecasting-results.md#tab-short-term-forecasting).

[Table S12](B-forecasting-results.md#tab-short-term-forecasting) extends the analysis to short-term time series forecasting. Evaluation metrics including SMAPE, MASE, and OWA indicate that RDTU maintains its leading position. In the weighted average analysis across all sampling intervals (Yearly, Quarterly, Monthly, Others), RDTU records the best performance (e.g., Average OWA of 0.859), and matches Time-LLM on OWA while achieving lower SMAPE (OWA 0.859), significantly surpassing traditional methods like N-HiTS and N-BEATS.

<a id="tab-short-term-forecasting"></a>

### Table S12

**Full M4 short-term forecasting results.** Lower values are better. Cells retain the numerical precision of the manuscript.

[Download all values (CSV)](../data/short-term-forecasting.csv).


#### Yearly

| Model | SMAPE | MASE | OWA |
| --- | ---: | ---: | ---: |
| **RDTU** | 13.408 | 3.014 | 0.788 |
| Time-LLM | 13.419 | 3.005 | 0.789 |
| GPT4TS | 15.11 | 3.565 | 0.911 |
| TimesNet | 15.378 | 3.554 | 0.918 |
| PatchTST | 13.477 | 3.019 | 0.792 |
| N-HiTS | 13.422 | 3.056 | 0.795 |
| N-BEATS | 13.487 | 3.036 | 0.795 |
| ETSformer | 18.009 | 4.487 | 1.115 |
| LightTS | 14.247 | 3.109 | 0.827 |
| DLinear | 16.965 | 4.283 | 1.058 |
| FEDformer | 14.021 | 3.036 | 0.811 |
| Stationary | 13.717 | 3.078 | 0.807 |
| Autoformer | 13.974 | 3.134 | 0.822 |
| Informer | 14.727 | 3.418 | 0.881 |
| Reformer | 16.169 | 3.800 | 0.973 |


#### Quarterly

| Model | SMAPE | MASE | OWA |
| --- | ---: | ---: | ---: |
| **RDTU** | 10.094 | 1.176 | 0.888 |
| Time-LLM | 10.110 | 1.178 | 0.889 |
| GPT4TS | 10.597 | 1.253 | 0.938 |
| TimesNet | 10.465 | 1.227 | 0.923 |
| PatchTST | 10.38 | 1.233 | 0.921 |
| N-HiTS | 10.185 | 1.18 | 0.893 |
| N-BEATS | 10.564 | 1.252 | 0.936 |
| ETSformer | 13.376 | 1.906 | 1.302 |
| LightTS | 11.364 | 1.328 | 1.000 |
| DLinear | 12.145 | 1.520 | 1.106 |
| FEDformer | 11.1 | 1.35 | 0.996 |
| Stationary | 10.958 | 1.325 | 0.981 |
| Autoformer | 11.338 | 1.365 | 1.012 |
| Informer | 11.360 | 1.401 | 1.027 |
| Reformer | 13.313 | 1.775 | 1.252 |


#### Monthly

| Model | SMAPE | MASE | OWA |
| --- | ---: | ---: | ---: |
| **RDTU** | 12.977 | 0.968 | 0.903 |
| Time-LLM | 12.980 | 0.963 | 0.903 |
| GPT4TS | 13.258 | 1.003 | 0.931 |
| TimesNet | 13.513 | 1.039 | 0.957 |
| PatchTST | 12.959 | 0.97 | 0.905 |
| N-HiTS | 13.059 | 1.013 | 0.929 |
| N-BEATS | 13.089 | 0.996 | 0.922 |
| ETSformer | 14.588 | 1.368 | 1.149 |
| LightTS | 14.014 | 1.053 | 0.981 |
| DLinear | 13.514 | 1.037 | 0.956 |
| FEDformer | 14.403 | 1.147 | 1.038 |
| Stationary | 13.917 | 1.097 | 0.998 |
| Autoformer | 13.958 | 1.103 | 1.002 |
| Informer | 14.062 | 1.141 | 1.024 |
| Reformer | 20.128 | 2.614 | 1.927 |


#### Others

| Model | SMAPE | MASE | OWA |
| --- | ---: | ---: | ---: |
| **RDTU** | 4.730 | 3.086 | 0.985 |
| Time-LLM | 4.795 | 3.178 | 1.006 |
| GPT4TS | 6.124 | 4.116 | 1.259 |
| TimesNet | 6.913 | 4.507 | 1.438 |
| PatchTST | 4.952 | 3.347 | 1.049 |
| N-HiTS | 4.711 | 3.054 | 0.977 |
| N-BEATS | 6.599 | 4.43 | 1.393 |
| ETSformer | 7.267 | 5.240 | 1.591 |
| LightTS | 15.880 | 11.434 | 3.474 |
| DLinear | 6.709 | 4.953 | 1.487 |
| FEDformer | 7.148 | 4.041 | 1.389 |
| Stationary | 6.302 | 4.064 | 1.304 |
| Autoformer | 5.485 | 3.865 | 1.187 |
| Informer | 24.460 | 20.960 | 5.879 |
| Reformer | 32.491 | 33.355 | 8.679 |


#### Average

| Model | SMAPE | MASE | OWA |
| --- | ---: | ---: | ---: |
| **RDTU** | 11.979 | 1.599 | 0.859 |
| Time-LLM | 11.983 | 1.595 | 0.859 |
| GPT4TS | 12.69 | 1.808 | 0.94 |
| TimesNet | 12.88 | 1.836 | 0.955 |
| PatchTST | 12.059 | 1.623 | 0.869 |
| N-HiTS | 12.035 | 1.625 | 0.869 |
| N-BEATS | 12.25 | 1.698 | 0.896 |
| ETSformer | 14.718 | 2.408 | 1.172 |
| LightTS | 13.525 | 2.111 | 1.051 |
| DLinear | 13.639 | 2.095 | 1.051 |
| FEDformer | 13.16 | 1.775 | 0.949 |
| Stationary | 12.780 | 1.756 | 0.930 |
| Autoformer | 12.909 | 1.771 | 0.939 |
| Informer | 14.086 | 2.718 | 1.230 |
| Reformer | 18.200 | 4.223 | 1.775 |


---
Source: full manuscript Appendix B. See the [coverage map](coverage.md) and [source notes](source-notes.md).
