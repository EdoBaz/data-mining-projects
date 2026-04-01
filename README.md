# Data Mining: Advanced Techniques & Applications

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook%2FLab-orange)
[![License](https://img.shields.io/badge/License-MIT-green)]()

A comprehensive collection of **4 advanced data mining projects** implementing state-of-the-art techniques for pattern discovery, optimization, scheduling, and time-series classification. Developed as university coursework focusing on practical algorithmic implementations and real-world applications.

---

## Authors
- Simone Xiao
- Edoardo Bazzotti

---

## 📋 Projects Overview

### 🔍 **Exercise 1: Quantitative Association Rules Mining**  
**File:** [`es1BCD.ipynb`](es1BCD.ipynb)

Implements an **Apriori-style algorithm** to extract quantitative association rules from Air Quality data. Key aspects:
- Dataset encoding and preprocessing (UCÌ Air Quality dataset)
- Pattern discovery using encoded features (CO, Temperature, Humidity, etc.)
- Statistical significance filtering using hypergeometric tests
- Parallel computation using `joblib` for performance optimization


---

### 💰 **Exercise 2: Coalition Payoff Optimization & Shapley Values**  
**File:** [`es2.ipynb`](es2.ipynb)

Analyzes coalition formation and value distribution using **game-theoretic approaches**. Key aspects:
- Coalition payoff optimization (CPO): finding optimal player coalitions
- Approximate Shapley value computation for fair payoff allocation
- Integration with Exercise 1 data preprocessing
- Application to Air Quality feature coalitions


---

### 📅 **Exercise 3: Stochastic Scheduling & Process Mining**  
**File:** [`es3.ipynb`](es3.ipynb)

Models **stochastic scheduling systems** and learns optimal policies using reinforcement learning. Key aspects:
- Definition of stochastic scheduling problems with temporal constraints
- Markov Decision Process (MDP) learning using AALpy
- Optimal policy computation for constraint satisfaction
- Event log generation and **Petri net discovery** using PM4Py
- Fair policy extraction and state coverage analysis

---

### 📈 **Exercise 4: Time Series Classification with Ensemble Methods**  
**File:** [`es4.ipynb`](es4.ipynb)

Implements advanced **ensemble-based time series classifiers** with conformal prediction. Key aspects:
- Sequential Boost Classifier (SBC) and variants (BE-SBC, I-SBC)
- Unsupervised clustering analysis on ECG and SmoothSubspace datasets
- **Conformal prediction** for calibrated confidence intervals
- Distance-based classification (nearest-neighbor variants)
- Comprehensive evaluation on binary and multiclass problems

---

## 🗂️ Project Structure

```
data-mining-projects/
├── es1BCD.ipynb                    # Quantitative association rules (Exercise 1 & 2)
├── es2.ipynb                       # Coalition payoff & Shapley values (Exercise 2)
├── es3.ipynb                       # Stochastic scheduling & MDPs (Exercise 3)
├── es4.ipynb                       # Time series classification (Exercise 4)
├── assignments/                    # Original assignment specifications (PDF)
│   ├── Es1e2.pdf
│   ├── Exercise 3.pdf
│   └── Exercise 4 (updated 19 Dec 2024).pdf
├── datasets/                       # Data files
│   ├── AirQualityUCI.csv          # Exercise 1-2: Air quality measurements
│   ├── ECG200_TRAIN.arff          # Exercise 4: ECG time series (train)
│   ├── ECG200_TEST.arff           # Exercise 4: ECG time series (test)
│   ├── SmoothSubspace_TRAIN.arff  # Exercise 4: Synthetic time series (train)
│   └── SmoothSubspace_TEST.arff   # Exercise 4: Synthetic time series (test)
├── requirements.txt                # Python dependencies
└── README.md                       # This file
```

---

## 🚀 Getting Started

### Prerequisites
- **Python 3.10+**
- **Git** (for cloning the repository)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/data-mining-projects.git
cd data-mining-projects
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

### Running the Notebooks

1. **Start Jupyter:**
```bash
jupyter lab
# or
jupyter notebook
```

2. **Open the desired notebook** (`es1BCD.ipynb`, `es2.ipynb`, `es3.ipynb`, or `es4.ipynb`)

3. **Run cells sequentially** from top to bottom

**Note:** Download the Air Quality dataset (see section below) before running Exercises 1 and 2.

---

## 📦 Dependencies

Core libraries used across projects:

| Package | Purpose |
|---------|---------|
| `numpy` / `pandas` | Numerical computing & data manipulation |
| `scikit-learn` | ML utilities (clustering, metrics) |
| `scipy` | Statistical tests (hypergeometric, etc.) |
| `joblib` | Parallel computation |
| `numba` | JIT compilation for performance |
| `nonconformist` | Conformal prediction |
| `aalpy` | MDP learning & synthesis |
| `pm4py` | Process mining (Petri nets, event logs) |
| `networkx` | Graph/network analysis |
| `pydot` | Graph visualization |
| `tabulate` | Pretty table formatting |

See [`requirements.txt`](requirements.txt) for exact versions.

---

## 📊 Datasets

### Air Quality (UCI)
- **Source:** UCI Machine Learning Repository - Air Quality Dataset
- **Format:** CSV (semicolon-separated)
- **Usage:** Exercises 1 & 2
- **Features:** CO, O₃, NOₓ, NMHC, NO₂, Temperature, Relative Humidity, Absolute Humidity
- **Location:** `datasets/AirQualityUCI.csv`
- **Required for:** es1BCD.ipynb, es2.ipynb

### Time Series Datasets (ARFF format)
- **ECG200:** Binary ECG classification (normal vs. abnormal heartbeats)
- **SmoothSubspace:** Synthetic multiclass time series data
- **Usage:** Exercise 4 (time series classification)
- **Location:** `datasets/ECG200_*.arff`, `datasets/SmoothSubspace_*.arff`

---

## ⚙️ Technical Highlights

### Performance Optimizations
- **Vectorized operations** with NumPy/Pandas instead of loops
- **Numba JIT compilation** (~2-3x speedup for stump finding in SBC)
- **Parallel processing** with `joblib` for independent tasks
- **LRU caching** for repeated subset evaluations (Shapley computation)

### Advanced Techniques Demonstrated
- **Statistical Testing:** Hypergeometric tests for rule significance
- **Ensemble Learning:** Sequential boosting with weak learners
- **Conformal Prediction:** Model-agnostic uncertainty quantification
- **Process Mining:** Automated discovery of process models (Petri nets)
- **Reinforcement Learning:** MDP-based policy synthesis
- **Game Theory:** Coalition analysis & Shapley value computation

---

## 📝 Notes

### Reproducibility
Some workflows involve **stochastic elements** (random sampling, stochastic task durations, train/calibration splits). Results may vary across runs unless random seeds are explicitly fixed in the code.

### Execution Times
Certain computations are computationally intensive:
- **Shapley value approximation** (Exercise 2): May take several minutes
- **MDP learning** (Exercise 3): Depends on state space size
- **Conformal calibration** (Exercise 4): O(n²) complexity in calibration set

Monitor cell execution times and adjust dataset sizes if needed for faster iteration during development.

---

## 🎓 Academic Context

These projects were developed as coursework for an advanced **Data Mining & Machine Learning** university course (2024/2025 academic year). Each exercise progresses in complexity and demonstrates how fundamental techniques scale to practical scenarios.

**Learning Outcomes:**
- Algorithmic thinking and implementation in Python
- Performance optimization techniques
- Practical data preprocessing and validation
- Understanding trade-offs between accuracy, efficiency, and interpretability

---

## 📄 Assignment Specifications

Complete assignment PDFs are included in the `assignments/` folder:
- [`assignments/Es1e2.pdf`](assignments/Es1e2.pdf) - Exercises 1 & 2
- [`assignments/Exercise 3.pdf`](assignments/Exercise%203.pdf) - Exercise 3
- [`assignments/Exercise 4 (updated 19 Dec 2024).pdf`](assignments/Exercise%204%20(updated%2019%20Dec%202024).pdf) - Exercise 4

