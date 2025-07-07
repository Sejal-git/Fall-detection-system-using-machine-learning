# 🧓 Fall Detection for Elderly People using Machine Learning

A real-time, machine learning–based fall detection system designed using wearable sensors to improve elderly care and reduce fatal injuries. The system utilizes a tri-axial accelerometer, advanced feature extraction, and multiple classification algorithms to distinguish between falls and normal daily activities with high accuracy.

---

## 📌 Project Highlights

- Uses **SisFall dataset** containing fall and non-fall activities
- Implements and compares **7 ML algorithms** using **10-fold cross-validation**
- Achieves **99.18% accuracy** using **Random Forest**
- Hardware prototype with accelerometer sensor on waist belt
- Alert mechanism for notifying caregivers in case of falls

---

## 🧠 Abstract

Due to lifestyle changes, many elderly people live alone, increasing the risk of unattended fall injuries. This system provides a reliable, wearable, sensor-based fall detection solution. Acceleration data from a tri-axial accelerometer is processed and analyzed to detect falls using machine learning algorithms. Among all tested models, **Random Forest** gave the best accuracy (99.18%). This solution is low-cost, non-invasive, and suitable for real-world use in elderly care.

---

## 🧰 Tech Stack

- **Programming Language:** Python 3.7+
- **Libraries:** Scikit-learn, Pandas, NumPy, Matplotlib
- **Hardware:** ADXL345 accelerometer (waist-mounted)
- **Tools:** VNC server, Jupyter Notebook
- **ML Models Used:** Random Forest, Decision Tree, KNN, SVM, Naïve Bayes, Logistic Regression, Neural Network

---

## 📁 Dataset

- Dataset: [SisFall Dataset](https://www.researchgate.net/publication/311964625_SisFall_A_Fall_and_Movement_Dataset)
- 19 daily activities + 15 fall types performed by 8 individuals
- Sample data: Over 1 lakh accelerometer readings
- Sensor axes: X, Y, Z

---

## ⚙️ Methodology

1. **Data Acquisition** using ADXL345
2. **Preprocessing** with Butterworth Filter (cutoff = 5Hz)
3. **Feature Extraction** (magnitude, std, sum, etc.)
4. **ML Classification** using multiple algorithms
5. **Real-Time Fall Detection**
6. **Alert Mechanism** for notifications

---

## 📊 Results

| Algorithm         | Accuracy  | Training Time | Prediction Time |
|------------------|-----------|----------------|------------------|
| KNN (K=15)        | 91.54%    | 0.031 s        | 0.39 s           |
| SVM               | 60.09%    | 4.259 s        | 3.76 s           |
| Naïve Bayes       | 96.89%    | 0.016 s        | 0.016 s          |
| Neural Network    | 75.01%    | 4.742 s        | 0.07 s           |
| Logistic Regression | 96.36%  | 9.995 s        | 0.08 s           |
| Decision Tree     | 97.00%    | 0.125 s        | 0.06 s           |
| ⭐ Random Forest    | **99.18%** | **1.154 s**     | **0.047 s**        |

---

## 🔧 Time Analysis

| Sample Size | Time Taken (No Fall) | Time Taken (Fall Detected) |
|-------------|----------------------|-----------------------------|
| 1000 (5 sec) | ~19–21 sec           | ~23–25 sec                  |
| 2000 (10 sec) | ~35–37 sec          | ~39–41 sec                  |

> ⏳ Time bottleneck observed in saving to DataFrame — can be optimized with faster microcontrollers.

---

## 🧪 Hardware Prototype

- Accelerometer mounted on waist
- Data read via VNC server
- Monitors posture:
  - **Upright** → No fall
  - **Bent or lying** → Fall detected

---

## 📈 Future Work

- Add **fall forecasting** using time-series data
- Reduce time overhead using **faster embedded hardware**
- Integrate **SMS/call alerts**
- Handle **complex ADL scenarios** for better generalization
