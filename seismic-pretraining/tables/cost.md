# Training cost of the 3-D models

Wall-clock hours of one single-GPU training run (mean ± sd over seeds). U-Net jobs were placed on whichever GPU class was free (A40 / L40S / A100 / A10), DINOv3 jobs on H100 except the N = 100 cells (A100 40 GB, one on an A40; about 1.8× and 3× the H100 time), so hours are indicative rather than a controlled comparison.

| model | N | n seeds | trainable params | steps | GPU hours / run | GPU class | test IoU |
|---|---:|---:|---:|---:|---|---|---|
| 3-D U-Net (from scratch) | 1 | 3 | 3.3 M | 60 k | 4.4 ± 2.3 | A40 / L40S / A100 / A10 (whichever was free) | 0.204 ± 0.113 |
| 3-D U-Net (from scratch) | 3 | 3 | 3.3 M | 60 k | 7.4 ± 2.3 | A40 / L40S / A100 / A10 (whichever was free) | 0.340 ± 0.014 |
| 3-D U-Net (from scratch) | 10 | 3 | 3.3 M | 60 k | 8.0 ± 1.7 | A40 / L40S / A100 / A10 (whichever was free) | 0.377 ± 0.004 |
| 3-D U-Net (from scratch) | 100 | 3 | 3.3 M | 60 k | 6.4 ± 0.8 | A40 / L40S / A100 / A10 (whichever was free) | 0.396 ± 0.014 |
| 3-D U-Net (from scratch) | 900 | 3 | 3.3 M | 60 k | 7.5 ± 2.3 | A40 / L40S / A100 / A10 (whichever was free) | 0.386 ± 0.003 |
| DINOv3 + 3-D decoder | 1 | 3 | 100.8 M | 10 k | 1.5 ± 0.0 | H100 (N = 100: A100 40 GB) | 0.325 ± 0.023 |
| DINOv3 + 3-D decoder | 3 | 5 | 100.8 M | 10 k | 1.5 ± 0.0 | H100 (N = 100: A100 40 GB) | 0.371 ± 0.012 |
| DINOv3 + 3-D decoder | 10 | 3 | 100.8 M | 10 k | 1.5 ± 0.0 | H100 (N = 100: A100 40 GB) | 0.391 ± 0.015 |
| DINOv3 + 3-D decoder | 100 | 3 | 100.8 M | 10 k | 2.7 ± 0.0 | H100 (N = 100: A100 40 GB) | 0.403 ± 0.009 |
| DINOv3 + 3-D decoder | 900 | 3 | 100.8 M | 10 k | 1.5 ± 0.0 | H100 (N = 100: A100 40 GB) | 0.408 ± 0.006 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 1 | 3 | 100.8 M | 10 k | 1.5 ± 0.0 | H100 (N = 100: A100 40 GB / A40) | 0.361 ± 0.020 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 3 | 5 | 100.8 M | 10 k | 1.5 ± 0.0 | H100 (N = 100: A100 40 GB / A40) | 0.384 ± 0.018 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 10 | 3 | 100.8 M | 10 k | 1.5 ± 0.0 | H100 (N = 100: A100 40 GB / A40) | 0.415 ± 0.015 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 100 | 3 | 100.8 M | 10 k | 3.4 ± 1.2 | H100 (N = 100: A100 40 GB / A40) | 0.413 ± 0.011 |
| DINOv3 + seismic I-JEPA + 3-D decoder | 900 | 3 | 100.8 M | 10 k | 1.5 ± 0.0 | H100 (N = 100: A100 40 GB / A40) | 0.414 ± 0.005 |
