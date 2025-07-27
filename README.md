# ⚙️ Robust Fault Detection in Noisy, Small-Scale IoT Datasets

This machine learning project identifies device malfunctions using limited and noisy system performance data. It replicates real-world sensor inconsistencies and resource constraints, showcasing how lightweight ML models can still achieve exceptional performance in industrial IoT environments.

📌 GitHub Repository: [kanishka-mohankumar/Fault-Rate-Detection](https://github.com/kanishka-mohankumar/Fault-Rate-Detection)

---

## 🎯 Project Snapshot

In real industrial setups, data is rarely abundant or clean. This project demonstrates:

- Low-volume data analysis (only 100 observations)
- Noise-corrupted features (to mimic sensor error)
- Critical fault detection needs with limited history
- Model effectiveness under uncertainty and imbalance

**Main Objective:** Deliver dependable fault detection using minimal data while maintaining resilience to signal noise.

---

## 💡 Realistic Constraints Addressed

Unlike typical academic examples, we introduce intentional imperfections:

- ✅ Tiny dataset size (100 entries)
- ✅ Artificial Gaussian noise to mirror sensor drift
- ✅ Unequal class distribution (reflecting fewer fault cases)
- ✅ Despite all constraints, >95% detection accuracy achieved

A true testbed for small-data ML solutions.

---

## 📊 Dataset Overview

Synthetic data was generated simulating device logs:

| Feature  | Range       | Description              | Noise Injected (σ) |
|----------|-------------|---------------------------|---------------------|
| Memory   | 0–100%      | RAM usage percentage       | ±5%                 |
| Traffic  | 0–200 MBps  | Network throughput         | ±10 MBps            |
| Latency  | 1–100 ms    | Response delay             | ±5 ms               |
| Fault    | 0 or 1      | Target variable (binary)   | -                   |

> Data Distribution:  
> - Total Samples: 100  
> - Normal Devices: 60  
> - Faulty Devices: 40  

---

## 🔊 Sensor Noise Simulation

Noise was systematically added using:

```python
def inject_noise(data, std_dev):
    noise = np.random.normal(0, std_dev, data.shape)
    return np.clip(data + noise, 0, np.max(data))
## ⚙️ How to Use

This project allows you to detect hardware faults using minimal and noisy data in a realistic IoT simulation.

### 📦 Requirements

- Python 3.8 or higher
- pip (Python package manager)
- Dependencies listed in `requirements.txt`

---

## 🔧 Setup Instructions

Follow these steps to set up and run the project locally:

```bash
# Step 1: Clone the repository
git clone https://github.com/kanishka-mohankumar/Fault-Rate-Detection.git
cd Fault-Rate-Detection

# Step 2: Install dependencies
pip install -r requirements.txt

# Step 3: Generate synthetic dataset with noise
python generate_device_data.py

# Step 4: Train and evaluate models
python fault_model.py

# Step 5: Make predictions using new data
python predict.py --memory 75 --traffic 120 --latency 45
## 🧠 Innovations and Contributions

### 🚀 Practical ML in Low-Data Environments

- Designed to perform fault detection with **only 100 samples**, ideal for IoT environments with minimal historical data.
- Introduces **Gaussian noise** to simulate **real-world sensor irregularities** and degradation.

### 🧪 Robust Evaluation Pipeline

- **Stratified 5-fold Cross-Validation** for balanced model training
- **Noise sensitivity tests** at multiple standard deviations (σ = 1, 5, 10, 15)
- **SHAP value analysis** for feature importance and model explainability
- **Confidence intervals** using bootstrap resampling for performance stability

### 💡 Model Simplicity vs. Performance

- Demonstrates that **simpler models like Logistic Regression** can outperform complex ones when data is scarce and noisy
- Highlights **interpretability, efficiency, and deployability** in constrained environments

---

## 🏆 Recognition

🥇 **Best Small Data ML Project – DataSet2024 Hackathon**  
🏢 Received **Internship Opportunity from Nokia**  
📌 Awarded for addressing real-world constraints in industrial IoT fault detection  
🎓 Project recognized for demonstrating **practicality over complexity** in machine learning deployment

---

## 📄 License

This project is licensed for **academic, educational, and research use**.

You are permitted to:

- Use and adapt the code for your own non-commercial projects
- Reference or modify the code with proper credit

📌 Please include attribution if publishing or distributing derived work based on this repository.

---

## 📚 Citation

If you use this project in your academic research, reports, or presentations, please cite it as follows:

## 🙋‍♂️ About the Author

[@kanishka-mohankumar](https://github.com/kanishka-mohankumar)
> Made with 💡 logic, 📊 data, and passion for real-world ML applications.
