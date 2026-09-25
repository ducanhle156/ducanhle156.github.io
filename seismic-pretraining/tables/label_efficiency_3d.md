# 3-D fault segmentation vs number of labelled inlines

Thebe test split (71 inlines), raw labels, threshold 0.5 for IoU/Dice; PR-AUC is threshold-free. Mean ± sd over seeds (3; DINOv3 models at N = 3: 5). 3-D U-Net: 3.3 M parameters, 60 k steps; DINOv3 models: 100.8 M trainable parameters, 10 k steps.

| model | N | n seeds | IoU | Dice | PR-AUC | per-seed IoU |
|---|---:|---:|---|---|---|---|
| 3-D U-Net (from scratch) | 1 | 3 | 0.204 ± 0.113 | 0.326 ± 0.167 | 0.267 ± 0.116 | 0.075, 0.258, 0.280 — seed 0 did not train (IoU 0.075); 2 trained seeds: IoU 0.269 ± 0.015 |
| 3-D U-Net (from scratch) | 3 | 3 | 0.340 ± 0.014 | 0.506 ± 0.015 | 0.467 ± 0.027 | 0.324, 0.342, 0.353 |
| 3-D U-Net (from scratch) | 10 | 3 | 0.377 ± 0.004 | 0.547 ± 0.004 | 0.541 ± 0.017 | 0.380, 0.378, 0.373 |
| 3-D U-Net (from scratch) | 100 | 3 | 0.396 ± 0.014 | 0.566 ± 0.015 | 0.583 ± 0.003 | 0.409, 0.380, 0.398 |
| 3-D U-Net (from scratch) | 900 | 3 | 0.386 ± 0.003 | 0.556 ± 0.003 | 0.574 ± 0.015 | 0.389, 0.385, 0.385 |
| DINOv3 + 3-D decoder | 1 | 3 | 0.325 ± 0.023 | 0.489 ± 0.027 | 0.418 ± 0.013 | 0.342, 0.298, 0.334 |
| DINOv3 + 3-D decoder | 3 | 5 | 0.371 ± 0.012 | 0.541 ± 0.013 | 0.519 ± 0.019 | 0.366, 0.380, 0.386, 0.356, 0.369 |
| DINOv3 + 3-D decoder | 10 | 3 | 0.391 ± 0.015 | 0.561 ± 0.015 | 0.568 ± 0.018 | 0.392, 0.405, 0.376 |
| DINOv3 + 3-D decoder | 100 | 3 | 0.403 ± 0.009 | 0.574 ± 0.009 | 0.594 ± 0.003 | 0.401, 0.396, 0.413 |
| DINOv3 + 3-D decoder | 900 | 3 | 0.408 ± 0.006 | 0.579 ± 0.007 | 0.597 ± 0.007 | 0.416, 0.405, 0.404 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 1 | 3 | 0.361 ± 0.020 | 0.529 ± 0.022 | 0.458 ± 0.034 | 0.380, 0.340, 0.364 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 3 | 5 | 0.384 ± 0.018 | 0.553 ± 0.019 | 0.534 ± 0.021 | 0.399, 0.355, 0.391, 0.377, 0.395 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 10 | 3 | 0.415 ± 0.015 | 0.586 ± 0.015 | 0.598 ± 0.015 | 0.410, 0.432, 0.403 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 100 | 3 | 0.413 ± 0.011 | 0.584 ± 0.011 | 0.610 ± 0.009 | 0.409, 0.405, 0.425 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 900 | 3 | 0.414 ± 0.005 | 0.585 ± 0.005 | 0.603 ± 0.002 | 0.415, 0.419, 0.409 |
