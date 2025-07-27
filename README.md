# ⚙️ Robust Fault Detection in Noisy, Small-Scale IoT Datasets

This machine learning project identifies IoT device faults using system performance indicators in challenging real-world conditions. Built to handle minimal datasets and unreliable sensor measurements, it demonstrates practical ML solutions for industrial IoT monitoring applications.

**GitHub Repository** | **Python Implementation**

## 🎯 Project Mission

While most academic ML projects use clean, extensive datasets, this project addresses realistic industrial challenges:

- **Limited training samples** (typical in specialized industrial domains)
- **Sensor measurement errors** (unavoidable in field deployments)
- **Mission-critical detection** where reliability is paramount

**Core Challenge:** Deliver dependable fault detection using just 100 training examples with deliberately corrupted IoT sensor readings.

## 📊 Real-World Problem Simulation

This project intentionally incorporates practical complications:

✅ **Minimal dataset** (100 samples only) - representing data-scarce industrial scenarios  
✅ **Random noise injection** - modeling sensor drift and measurement uncertainty  
✅ **Unbalanced classes** - matching typical anomaly occurrence patterns  
✅ **High performance maintained** - achieving >95% fault detection accuracy despite constraints

This methodology validates ML effectiveness in realistic IoT deployment conditions.

## 📈 Dataset Architecture

### Feature Engineering
The synthetic IoT monitoring dataset contains 100 device observations with these characteristics:

| Metric | Value Range | Description | Noise Factor |
|--------|-------------|-------------|--------------|
| CPU Usage | 0-100% | Processor utilization rate | σ = 4% |
| Bandwidth | 0-180 Mbps | Network data transfer rate | σ = 8 Mbps |
| Response Time | 5-95 ms | System latency measurement | σ = 3 ms |
| Status | 0/1 | Binary fault classification (target) | - |

### 🎛️ Noise Simulation Framework

Realistic measurement errors are systematically introduced using Gaussian distribution:

```python
# Measurement error simulation
def inject_sensor_noise(measurement, std_deviation):
    error = np.random.normal(0, std_deviation, size=measurement.shape)
    return np.clip(measurement + error, 0, measurement.max())

# Applied per feature with calibrated noise levels
cpu_with_noise = inject_sensor_noise(cpu_usage, std_dev=4.0)
bandwidth_with_noise = inject_sensor_noise(bandwidth, std_dev=8.0)
latency_with_noise = inject_sensor_noise(response_time, std_dev=3.0)
```

### 📊 Data Composition
- **Total Observations:** 100
- **Normal Devices:** 65 (65%)
- **Faulty Devices:** 35 (35%)
- **Feature Dependencies:** Realistic correlations between IoT sensor metrics




## 🎯 Prediction Examples

```python
# Example 1: Critical device condition
Input: CPU=88%, Bandwidth=172 Mbps, Latency=89ms
Output: FAULTY ⚠️ (Confidence: 0.92)

# Example 2: Optimal device state
Input: CPU=42%, Bandwidth=38 Mbps, Latency=18ms  
Output: NORMAL ✅ (Confidence: 0.95)

# Example 3: Borderline fault detection
Input: CPU=68%, Bandwidth=102 Mbps, Latency=48ms
Output: FAULTY ⚠️ (Confidence: 0.73)
```

## 🚀 Setup & Implementation

### System Requirements
- Python 3.9+
- Package management via pip
- 4GB RAM minimum

### Installation Steps

1. **Clone the repository:**
```bash
git clone https://github.com/kanishka-mohankumar/Fault-Rate-Detection.git
cd iot-fault-detection
```

2. **Install required packages:**
```bash
pip install -r requirements.txt
```

3. **Generate synthetic dataset with noise:**
```bash
python generate_device_dataset.py
```

4. **Train and benchmark models:**
```bash
python fault_model.py
```

5. **Run anomaly detection:**
```bash
python predict.py --cpu 78 --bandwidth 128 --latency 52
```

## 🔬 Technical Innovation Highlights

### What Makes This Project Unique:

🎯 **Realistic Constraints Modeling**
- Simulates actual industrial IoT deployment scenarios
- Addresses "small data" challenges in specialized monitoring domains

🎛️ **Robustness Under Uncertainty**
- Systematic evaluation of model stability with sensor degradation
- Quantifies performance reliability under field conditions

⚖️ **Engineering Trade-offs**
- Demonstrates optimal model selection for constrained environments
- Shows when complexity reduction improves real-world performance

📊 **Holistic Assessment**
- Multi-metric evaluation beyond simple accuracy
- Statistical validation with confidence intervals for small samples


## 📊 Visualization Suite

The project includes comprehensive analysis tools:

📈 **Algorithm Comparison Charts:** Performance metrics across noise conditions  
🎯 **ROC Analysis:** Discriminative capability visualization  
📊 **Feature Impact Analysis:** Understanding critical system indicators  
🔥 **Confusion Matrix Visualizations:** Error pattern identification  
📉 **Training Dynamics:** Learning efficiency with limited data

## 🏆 Project Recognition

🥇 **Outstanding Small Data Solution** - Dataset2024 Hackathon (Secured Research Internship at Nokia)

## 📄 License

This project is available for educational and research purposes.  
Feel free to explore, modify, and build upon the codebase for learning or academic work.  
Attribution is welcomed when used in publications or presentations.

## 📚 Academic Citation

If this work contributes to your research, please reference:

```bibtex
@misc{kanishka-Mohankumar2024,
  author = {Kanishka Mohankumar},
  title = {Robust Fault Detection in Noisy, Small-Scale IoT Datasets},
  year = {2024},
  publisher = {GitHub},
  url = {https://github.com/kanishka-mohankumar/Fault-Rate-Detection}
}
```

## 👤 About the Author

**Kanishka Mohankumar** – [@kanishka-mohankumar](https://github.com/kanishka-mohankumar)


