# Fetal Arrhythmia Detection using Deep Learning

Implementation of a CNN-based approach to detect fetal arrhythmia from ECG signals.

---

## Dataset

PhysioNet Non-Invasive Fetal ECG Dataset

* 14 Normal (NR)
* 12 Arrhythmia (ARR)

---

## Approach

1. **Load ECG signals** using `wfdb`
2. **Segment signals** into 3s windows (1s stride)
3. **Label segments using RR-interval variability**

   * Low variance → Normal
   * High variance → Arrhythmia
   * Mid-range → ignored
4. **Train 1D CNN** on clean segments
5. **Subject-level prediction** using ratio of arrhythmic segments

---

## Model

* Conv1D → ReLU
* Conv1D → ReLU
* MaxPooling
* Fully Connected
* Output (2 classes)

---

## Results

* ~68% (random split)
* ~83% (subject-wise split)
* ~90%+ (with RRI-based filtering)

---

## Tech Stack

Python, PyTorch, NumPy, SciPy, WFDB

---

## Run

```bash
pip install wfdb torch numpy scipy matplotlib
```

Run the training script/notebook after placing dataset files.

---
