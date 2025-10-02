--- 
tags: [#ml #math]
created: 01-10-2025
--- 
## 🔹 Definition / Formula

Model calibration is typically defined by the relationship between the predicted probability and the true frequency of outcomes. The goal is often expressed as minimizing a specific scoring rule, such as the **Expected Calibration Error (ECE)**.

ECE=m=1∑M​N∣Bm​∣​∣acc(Bm​)−conf(Bm​)∣

---

## 🔹 Explanation (in my words)

Model calibration is a post-processing step that ensures the predicted probabilities from a classifier accurately reflect the **true likelihood** of an event. It answers the question: "When my model says it's **80% sure** an event will happen, does that event actually occur **80% of the time**?" A well-calibrated model is one that you can **trust** to give reliable confidence estimates, not just correct classifications.

---

## 🔹 Components

|Variable / Symbol|Meaning|
|---|---|
|ECE|**Expected Calibration Error** (The metric used to quantify miscalibration).|
|M|The total number of equally sized **bins** or intervals (e.g., 0−0.1,0.1−0.2,…) used to group predictions.|
|Bm​|The set of samples falling into the m-th confidence bin.|
|N|The total number of samples in the calibration set.|
|$\frac{|B_m|
|acc(Bm​)|The **accuracy** (true frequency) of samples within bin Bm​. (The proportion of correct predictions in that bin).|
|conf(Bm​)|The **confidence** (average predicted probability) of samples within bin Bm​.|
|$|\text{acc}(B_m) - \text{conf}(B_m)|


---

## 🔹 Context

- **Where it’s used:** Primarily used in **Machine Learning**, especially in fields where risk assessment and trust are critical: **Medical Diagnosis** (e.g., predicting disease probability), **Financial Risk Modeling**, and **Autonomous Systems**.
    
- **When it appears:** It's often required **after training complex, high-capacity models** like **Random Forests** or **Deep Neural Networks**, which are known to be prone to **over-confidence** (i.e., poor calibration) due to minimizing a cross-entropy loss function.
    

---

## 🔹 Related

[[Classification Metrics]] - [[Platt Scaling]] - [[Isotonic Regression]]

---

## 🔹 Examples / Applications

**Case Study: The Reliability Diagram**

A **Reliability Diagram** (or Calibration Plot) visually assesses calibration. It plots the average accuracy in each bin against the average confidence for that bin.

- **Perfect Calibration** occurs when the points fall exactly on the **diagonal line** (y=x).
    
- The example below shows an **uncalibrated model** (often deep networks) that is consistently over-confident (its confidence is higher than its accuracy). A calibrated model would have its points closer to the diagonal.
    

---

## 🔹 Source

- **Paper/book:** [Guo, C., Pleiss, G., Sun, Y., & Weinberger, K. Q. (2017). On calibration of modern neural networks. In _International conference on machine learning_ (pp. 1321-1330). PMLR.] (This is the seminal work formalizing ECE and analyzing calibration in deep learning.)