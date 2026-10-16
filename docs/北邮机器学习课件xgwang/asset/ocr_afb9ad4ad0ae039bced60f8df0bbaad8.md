# Unsupervised DA method: DSN (3.2)

Table 1: Mean classification accuracy (%) for the unsupervised domain adaptation scenarios we evaluated all the methods on. We have replicated the experiments from Ganin et al. [8] and in parentheses we show the results reported in their paper. The “Source–only” and “Target–only” rows are the results on the target domain when using no domain adaptation and training only on the source or the target domain respectively. The results that perform best in each domain adaptation task are in bold font.

| Model | MNIST to MNIST-M | Synth Digits to SVHN | SVHN to MNIST | Synth Signs to GTSRB |
|---|---|---|---|---|
| Source-only | 56.6 (52.2) | 86.7 (86.7) | 59.2 (54.9) | 85.1 (79.0) |
| CORAL [27] | 57.7 | 85.2 | 63.1 | 86.9 |
| MMD [30, 18] | 76.9 | 88.0 | 71.1 | 91.1 |
| DANN [8] | 77.4 (76.6) | 90.3 (91.0) | 70.7 (73.8) | 92.9 (88.6) |
| DSN w/ MMD (ours) | 80.5 | 88.5 | 72.2 | 92.6 |
| DSN w/ DANN (ours) | 83.2 | 91.2 | 82.7 | 93.1 |
| Target-only | 98.7 | 92.4 | 99.5 | 99.8 |