# 2-D encoder benchmark (900 labelled Thebe inlines, LoRA r = 4, 10 k steps)

Test ODS IoU / Dice on the skeletonised convention (§B.4, values ~0.1 by construction) and threshold-free PR-AUC against raw labels. Track C = DINOv3 ViT-B/16 + seismic adaptation; track A = ViT-S/16 trained from scratch on seismic; K = control.

| encoder | track | n seeds | ODS IoU | ODS Dice | PR-AUC | per-seed IoU |
|---|---|---:|---|---|---|---|
| I-JEPA-adapted DINOv3 | C | 3 | 0.1091 ± 0.0028 | 0.1961 ± 0.0047 | 0.4452 ± 0.0112 | 0.1124, 0.1075, 0.1074 |
| VISReg-adapted (+ Poseidon) | C | 3 | 0.1050 ± 0.0047 | 0.1895 ± 0.0078 | 0.4135 ± 0.0161 | 0.1098, 0.1049, 0.1004 |
| I-JEPA-adapted (+ Poseidon) | C | 3 | 0.0990 ± 0.0043 | 0.1796 ± 0.0071 | 0.4073 ± 0.0144 | 0.0993, 0.1032, 0.0947 |
| VISReg-adapted | C | 3 | 0.0971 ± 0.0026 | 0.1763 ± 0.0044 | 0.3791 ± 0.0035 | 0.0984, 0.0941, 0.0989 |
| DINOv3 as released | C | 3 | 0.0925 ± 0.0039 | 0.1690 ± 0.0065 | 0.3949 ± 0.0172 | 0.0944, 0.0951, 0.0881 |
| DINOv2-adapted | C | 3 | 0.0898 ± 0.0034 | 0.1644 ± 0.0057 | 0.3822 ± 0.0027 | 0.0932, 0.0897, 0.0865 |
| DINOv2-adapted (+ Poseidon) | C | 3 | 0.0885 ± 0.0037 | 0.1621 ± 0.0062 | 0.3696 ± 0.0118 | 0.0858, 0.0927, 0.0870 |
| SimMIM-adapted (legacy) | C | 3 | 0.0457 ± 0.0132 | 0.0872 ± 0.0240 | 0.1574 ± 0.0163 | 0.0609, 0.0394, 0.0368 |
| MAE-adapted | C | 1 | 0.0111 | 0.0220 | 0.0464 | 0.0111 |
| MAE (ViT-S/16 from scratch) | A | 3 | 0.0504 ± 0.0007 | 0.0958 ± 0.0013 | 0.1857 ± 0.0162 | 0.0496, 0.0510, 0.0506 |
| I-JEPA (ViT-S/16 from scratch) | A | 3 | 0.0439 ± 0.0009 | 0.0840 ± 0.0016 | 0.1705 ± 0.0045 | 0.0445, 0.0444, 0.0429 |
| VISReg (ViT-S/16 from scratch) | A | 3 | 0.0430 ± 0.0035 | 0.0823 ± 0.0064 | 0.1810 ± 0.0045 | 0.0454, 0.0390, 0.0446 |
| random init (ViT-S/16 from scratch) | A | 3 | 0.0422 ± 0.0037 | 0.0809 ± 0.0068 | 0.1571 ± 0.0023 | 0.0459, 0.0420, 0.0385 |
| DINOv2 (ViT-S/16 from scratch) | A | 3 | 0.0340 ± 0.0008 | 0.0657 ± 0.0014 | 0.1386 ± 0.0055 | 0.0344, 0.0331, 0.0344 |
| 2-D U-Net (supervised only) | K | 3 | 0.0774 ± 0.0029 | 0.1433 ± 0.0051 | 0.2425 ± 0.0053 | 0.0767, 0.0806, 0.0748 |
