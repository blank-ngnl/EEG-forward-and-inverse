# EEG forward and inverse
## Setup
Install MNE-python
```
conda create --name=mne python=3.8
conda activate mne
conda env update --file environment.yml
```

### Table 1: Performance of the Proposed Method across Various Models

| Model                    | Mean/Std             |
|--------------------------|----------------------|
| EEGNet                   | 72.33/10.19          |
| **EEGNet+**              | **87.33/5.71***      |
| EEG-Inception            | 73.28/10.02          |
| **EEG-Inception+**       | **76.65/9.78***      |
| LDA                      | 72.42/11.00          |
| **LDA+**                 | **85.18/6.83***      |
| LDA (FBCSP)              | 80.87/9.79           |
| SVM                      | 77.47/9.07           |
| **SVM+**                 | **87.86/5.75***      |
| SVM (FBCSP)              | 80.80/9.66           |
| RF                       | 75.53/10.12          |
| **RF+**                  | **86.32/5.59***      |
| RF (FBCSP)               | 82.39/10.73          |
| AdaBoost                 | 76.67/7.67           |
| **AdaBoost+**            | **85.67/6.26***      |
| AdaBoost (FBCSP)         | 79.04/10.75          |

**Note:**
- `+` indicates models trained with the enhanced EEG signals.
- `LDA`: Linear discriminant analysis.
- `SVM`: Support vector machine.
- `RF`: Random forest.
- `*`: p < 0.05.

### Table 2: Performance of the Proposed Method Using Different Attention Model (EEGNet - 22 EEG channels)

| Model            | Mean/Std           | Time (ms) |
|------------------|--------------------|-----------|
| OE               | 72.33/10.19        | 29.91     |
| MC (AL-I)        | 78.93/5.99*        | 226.01    |
| MC (AL-II)       | 81.38/8.40*        | 224.99    |
| MC (ML-I)        | 87.33/5.71*        | 213.99    |
| MC (ML-II)       | 78.93/5.99*        | 206.00    |
| MC (RD)          | 78.60/6.26*        | 193.99    |

**Note:**
- `OE`: original EEG.
- `AL-I`: attention layer-I.
- `AL-II`: attention layer-II.
- `ML-I`: mask layer-I.
- `ML-II`: mask layer-II.
- `RD`: random dropout.
- `*`: p < 0.05.

### Table 3: Performance of the Proposed Method Using Different ROI (EEGNet - 22 EEG channels)

| ROI   | Mean/Std           | Time (ms) |
|-------|--------------------|-----------|
| OE    | 72.33/10.19        | 29.91     |
| PMC   | 73.22/6.89         | 215.43    |
| MC    | 78.68/6.38*        | 212.90    |

**Note:**
- `OE`: original EEG.
- `PMC`: primary motor cortex.
- `MC`: motor-related cortex.
- `*`: p < 0.05.

### Table 4: Performance of the Proposed Method in Motor Imagery Task (EEGNet) (22 EEG channels)

| Subject | OE    | PMC   | MC    | MC (AL-I) | MC (AL-II) | MC (ML-I)  | MC (ML-II) | MC (RD) |
|---------|-------|-------|-------|-----------|------------|------------|------------|---------|
| A01     | 65.59 | 76.73*| 76.01*| 78.50*    | 75.99*     | **86.03*** | 77.44*     | 76.00*  |
| A02     | 62.94 | 68.69 | 71.21*| 72.28*    | 72.27*     | **85.60*** | 71.56*     | 70.13*  |
| A03     | 75.52 | 75.16 | 79.54*| 80.66     | 82.84*     | **84.29*** | 79.91*     | 78.79*  |
| A04     | 65.31 | 71.02 | 70.61 | 71.84*    | 71.02*     | **75.51*** | 68.98      | 71.84   |
| A05     | 92.43 | 70.81 | 85.60 | 88.26     | 89.79      | **94.30**  | 86.36      | 86.34   |
| A06     | 62.03 | 59.75 | 71.94*| 67.46*    | 71.08*     | **83.71*** | 75.12*     | 72.41*  |
| A07     | 85.73 | 77.68 | 86.46 | 84.61     | 86.81      | **94.48*** | 83.91      | 83.18   |
| A08     | 75.55 | 72.54 | 78.95 | 89.08*    | 89.08*     | **90.99*** | 79.69      | 79.69*  |
| A09     | 65.84 | 86.59*| 87.80*| 92.28*    | **93.51*** | 91.04*    | 87.39*     | 89.02*  |
| Mean /Std | 72.33 /10.19 | 73.22 /6.89 | 78.68 /6.38* | 78.93 /5.99* | 81.38 /8.40* | **87.33 /5.71*** | 78.93 /5.99* | 78.60 /6.26* |
|Time (ms) | 29.91 | 215.43 | 212.90 | 226.01 | 224.99 | 213.99 | 206.00 | 193.99 |

**Note:**
- `OE`: original EEG.
- `PMC`: primary motor cortex.
- `MC`: motor-related cortex.
- `AL-I`: attention layer-I.
- `AL-II`: attention layer-II.
- `ML-I`: mask layer-I.
- `ML-II`: mask layer-II.
- `RD`: random dropout.
- `*`: p < 0.05.
- `**`: indicates the highest value for that subject in bold.

### Table 5: Performance of the Proposed Method in Motor Imagery Task (EEG-Inception) with channel-wise normalization (22 EEG channels)

| Subject | OE    | PMC   | MC    | MC (AL-I) | MC (AL-II) | MC (ML-I)  | MC (ML-II) | MC (RD) |
|---------|-------|-------|-------|-----------|------------|------------|------------|---------|
| A01     | 68.44 | 61.66 | 65.23 | 64.16     | 63.07      | **83.49*** | 68.82      | 63.09   |
| A02     | 58.29 | 56.81 | 65.12 | 62.59*    | 63.63      | 64.38      | **66.56*** | 62.92   |
| A03     | 69.69 | 68.63 | 70.40 | 69.68     | 71.90      | **78.83*** | 71.91      | 66.80   |
| A04     | 64.90 | **65.71** | 64.90 | 58.37     | 60.82      | 63.27      | 63.67      | 60.41   |
| A05     | 90.15 | 63.27 | 80.67 | 81.82     | 79.89      | **90.91**  | 75.40      | 78.03   |
| A06     | 63.88 | 58.35 | 62.42 | 55.22     | 64.28      | **64.74**  | 59.73      | 58.81   |
| A07     | 82.80 | 72.15 | 74.02 | 80.96     | 78.77      | **87.93*** | 80.60      | 78.72   |
| A08     | **80.44** | 56.38 | 75.19 | 69.13     | 66.93      | 77.04      | 67.67      | 70.27   |
| A09     | **80.92** | 80.48 | 76.41 | 67.49     | 74.39      | 79.27      | 71.58      | 73.94   |
| Mean /Std | 73.28 /10.02 | 64.83 /7.48 | 70.49 /6.02 | 67.71 /8.58 | 69.30 /6.74 | **76.65 /9.78*** | 69.55 /5.87 | 68.11 /7.07 |
|Time (ms)| 37.99 | 200.01 | 205.00 | 223.99 | 226.02 | 211.00 | 207.57 | 201.00 |

**Note:**
- `OE`: original EEG.
- `PMC`: primary motor cortex.
- `MC`: motor-related cortex.
- `AL-I`: attention layer-I.
- `AL-II`: attention layer-II.
- `ML-I`: mask layer-I.
- `ML-II`: mask layer-II.
- `RD`: random dropout.
- `*`: p < 0.05.
- `**`: indicates the highest value for that subject in bold.

### Table 6: Performance of the Proposed Method in Motor Task (Machine Learning Model) (22 EEG channels)

| Subject | LDA   | LDA+  | SVM   | SVM+  | RF    | RF+   | AdaBoost | AdaBoost+ |
|---------|-------|-------|-------|-------|-------|-------|----------|-----------|
| A01     | 65.23 | **83.88** * | 69.53 | **86.39** * | 69.16 | **78.14** * | 65.96 | **79.20** * |
| A02     | 64.71 | **81.64** * | 66.18 | **81.30** * | 60.77 | **86.33** * | 73.74 | **83.45** * |
| A03     | 70.82 | **86.10** * | 76.24 | **87.95** * | 75.89 | **89.40** * | 76.28 | **84.67** * |
| A04     | 71.84 | **82.04** * | 75.92 | **83.27** * | 76.73 | **84.49** | 76.73 | **85.71** * |
| A05     | 92.42 | **95.08** | 91.66 | **94.70** * | 92.81 | **93.55** | 88.26 | **95.46** * |
| A06     | 63.83 | **81.93** * | 74.66 | **84.63** * | 66.05 | **84.14** * | 70.61 | **83.26** * |
| A07     | 86.81 | **94.11** * | 88.65 | **95.22** * | 82.75 | **87.54** | 83.16 | **91.93** * |
| A08     | 69.92 | **83.83** * | 75.18 | **88.70** * | 76.33 | **83.45** * | 74.04 | **80.45** * |
| A09     | 66.23 | **78.00** * | 79.25 | **88.60** * | 79.24 | **89.81** * | 81.27 | **86.96** |
| Mean / Std | 72.42 / 11.00 | **85.18 / 6.83** * | 77.47 / 9.07 | **87.86 / 5.75** * | 75.53 / 10.12 | **86.32 / 5.59** * | 76.67 / 7.67 | **85.67 / 6.26** * |
|Time (ms) | 0.00 | 182.00 | 22.00 | 187.00 | 6.00 | 170.00 | 9.00 | 168.99 |

---

**Note:**

- `LDA`: Linear Discriminant Analysis.
- `LDA+`: Enhanced Linear Discriminant Analysis.
- `SVM`: Support Vector Machine.
- `SVM+`: Enhanced Support Vector Machine.
- `RF`: Random Forest.
- `RF+`: Enhanced Random Forest.
- `AdaBoost`: AdaBoost.
- `AdaBoost+`: Enhanced AdaBoost.
- `*`: p < 0.05.
- `**`: Indicates the highest value for that subject in bold.

### Table 7: Performance of the Proposed Method in Motor Task (Machine Learning Model) using CSP (22 EEG channels)

| Subject | LDA   | SVM   | RF    | AdaBoost |
|---------|-------|-------|-------|----------|
| A01     | 86.75 | 87.82 | 87.81 | 85.30    |
| A02     | 60.81 | 60.42 | 58.62 | 60.07    |
| A03     | 89.42 | 88.67 | 90.88 | 89.77 |
| A04     | 77.55 | 75.10 | 76.33 | 66.94 |
| A05     | 82.55 | 82.93 | 85.20 | 80.67    |
| A06     | 67.87 | 69.68 | 71.95 | 67.46 |
| A07     | 84.26 | 84.60 | 86.07 | 82.44    |
| A08     | 92.10 | 90.21 | 93.99 | 92.49 |
| A09     | 86.57 | 87.78 | 90.64 | 86.19 |
| Mean / Std | 80.87 / 9.79 | 80.80 / 9.66 | 82.39 / 10.73 | 79.91 / 11.50 |
| Time (ms) | 0.00 | 0.00 | 7.98 | 6.97 |
---

**Note:**

- `LDA`: Linear Discriminant Analysis.
- `SVM`: Support Vector Machine.
- `RF`: Random Forest.
- `AdaBoost`: AdaBoost.

### Figure 1: Topographic maps visualization of subject 9

The chosen time points are 0s, 0.665s, 1.331s, and 1.996s out of the 2s-long duration. 

- **(a)** Preprocessed EEG signals (left-hand)
- **(b)** Preprocessed EEG signals (right-hand)
- **(c)** Enhanced EEG signals (left-hand)
- **(d)** Enhanced EEG signals (right-hand)

![Topomap:subject 9 original label 0](Figure/subject%209%20original%20label%200.png)
![Topomap:subject 9 original label 1](Figure/subject%209%20original%20label%201.png)

![Topomap:subject 9 enhanced label 0](Figure/subject%209%20enhanced%20label%200.png)
![Topomap:subject 9 enhanced label 1](Figure/subject%209%20enhanced%20label%201.png)

### Figure 2: Time domain visualization of subject 9

- **(a)** Preprocessed EEG signals (left-hand)
- **(b)** Preprocessed EEG signals (right-hand)
- **(c)** Enhanced EEG signals (left-hand)
- **(d)** Enhanced EEG signals (right-hand)

![Time:subject 9 original label 0](Figure/subject%209%20original%20label%200%20c3Z4.png)
![Time:subject 9 original label 1](Figure/subject%209%20original%20label%201%20c3Z4.png)

![Time:subject 9 enhanced label 0](Figure/subject%209%20enhanced%20label%200%20c3Z4.png)
![Time:subject 9 enhanced label 1](Figure/subject%209%20enhanced%20label%201%20c3Z4.png)

### Figure 3: Mask layer visualization in the motor imagery experiment

- **(a)** Motor-related cortex, all weights are preserved
- **(b)** Subject 1, weights from the model with the highest accuracy
- **(c)** Subject 9, weights from the model with the highest accuracy
- **(d)** Subject 9, weights from the model with the second highest accuracy

<img src="Figure/subject%203%201.0%20no%20binary.png" width="200" />
<img src="Figure/subject%201%2089.28.png" width="200" />
<img src="Figure/subject%209%2097.95.png" width="200" />
<img src="Figure/subject%209%2094.00.png" width="200" />