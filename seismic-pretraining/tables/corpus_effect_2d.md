# Pre-training corpus: Thebe vs Thebe + Poseidon (2-D benchmark, 900 labelled inlines, LoRA r = 4)

| recipe | corpus | n seeds | ODS IoU | PR-AUC | per-seed IoU |
|---|---|---:|---|---|---|
| I-JEPA-adapted | Thebe | 3 | 0.1091 ± 0.0028 | 0.4452 ± 0.0112 | 0.1124, 0.1075, 0.1074 |
| I-JEPA-adapted | Thebe + Poseidon | 3 | 0.0990 ± 0.0043 | 0.4073 ± 0.0144 | 0.0993, 0.1032, 0.0947 |
| VISReg-adapted | Thebe | 3 | 0.0971 ± 0.0026 | 0.3791 ± 0.0035 | 0.0984, 0.0941, 0.0989 |
| VISReg-adapted | Thebe + Poseidon | 3 | 0.1050 ± 0.0047 | 0.4135 ± 0.0161 | 0.1098, 0.1049, 0.1004 |
| DINOv2-adapted | Thebe | 3 | 0.0898 ± 0.0034 | 0.3822 ± 0.0027 | 0.0932, 0.0897, 0.0865 |
| DINOv2-adapted | Thebe + Poseidon | 3 | 0.0885 ± 0.0037 | 0.3696 ± 0.0118 | 0.0858, 0.0927, 0.0870 |
