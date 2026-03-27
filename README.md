# FutureFit AI Career Guidance System

An AI-powered career recommendation system that uses **LSTM deep learning** to provide personalized career guidance based on a student's skills, interests, and educational background.

Developed by Pragya Mishra & Bindu Sri Manne
Kennesaw State University, Dept. of Computer Science  

---

## Table of Contents
- [About the Project](#about-the-project)
- [Features](#features)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Libraries & Dependencies](#libraries--dependencies)
- [How to Run the Project](#how-to-run-the-project)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Future Work](#future-work)

---

## About the Project

Career decision-making is complex and influenced by personal interests, academic background, and evolving job market trends. Traditional counselling methods often lack scalability and personalization.

The **FutureFit Guidance System** addresses these challenges by:
- Using **LSTM (Long Short-Term Memory)** networks to analyze sequential career preference data
- Providing **evidence-based, personalized career recommendations**
- Integrating **bias mitigation strategies** and **explainable AI (XAI)** techniques
- Offering an intuitive **Gradio-based interface** accessible to non-technical users

---

## Features

- Personalized career recommendations based on 59 interest indicators
- Comparison of multiple ML models: Decision Tree, KNN, and LSTM
- Fine-tuned models using GridSearchCV and Keras callbacks
- Training and validation accuracy/loss visualizations
- 100% accuracy achieved on test data with the LSTM model

---

## Dataset

**File:** `stud.csv`

The dataset contains **59 binary interest features** (0 or 1) capturing student preferences across domains such as:

| Category | Examples |
|----------|---------|
| Creative Arts | Drawing, Dancing, Singing, Acting, Designing |
| Technical Skills | Coding, Electricity Components, Computer Parts, Engineering |
| Sciences | Physics, Chemistry, Biology, Botany, Zoology |
| Humanities | History, Literature, Sociology, Psychology, Geography |
| Languages | Hindi, French, English, Urdu |
| Others | Sports, Yoga, Journalism, Business, Photography |

**Target variable:** `Courses` — the recommended educational/career path (e.g., B.Sc. Engineering, B.A. Arts, etc.)

---

## Project Structure

```
FutureFit-AI-Career-Guidance-System/
│
├── FutureFit_Guidance.ipynb          # Main Jupyter Notebook (model training & evaluation)
├── FutureFit Guidance System.docx    # Full project report
├── stud.csv                          # Student interest dataset
├── README.md                         # Project documentation
├── LICENSE                           # MIT License
└── .gitignore                        # Python gitignore
```

---

## Libraries & Dependencies

Install all required libraries using pip:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow gradio
```

| Library | Purpose |
|--------|---------|
| `numpy` | Numerical computations |
| `pandas` | Data loading and preprocessing |
| `matplotlib` | Plotting training/validation curves |
| `seaborn` | Data visualization |
| `scikit-learn` | Decision Tree, KNN, LabelEncoder, GridSearchCV, metrics |
| `tensorflow` / `keras` | Building and training the LSTM model |
| `gradio` | Interactive user interface |

**Python version:** 3.8 or above recommended.

---

## How to Run the Project

### Step 1 — Clone the repository
```bash
git clone https://github.com/PragyaM-1907/FutureFit-AI-Career-Guidance-System.git
cd FutureFit-AI-Career-Guidance-System
```

### Step 2 — Install dependencies
```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow gradio
```

### Step 3 — Launch Jupyter Notebook
```bash
jupyter notebook FutureFit_Guidance.ipynb
```

### Step 4 — Run all cells
In the notebook, click **Kernel → Restart & Run All** to execute the full pipeline:
1. Data loading and preprocessing
2. Feature engineering
3. Model training (Decision Tree, KNN, LSTM)
4. Fine-tuning
5. Evaluation and visualizations

---

## Model Architecture

The core prediction engine uses a **stacked LSTM network**:

```
Input Layer  →  (1, 59 features)
LSTM Layer 1 →  128 units, return_sequences=True
Dropout      →  0.2
LSTM Layer 2 →  64 units
Dropout      →  0.2
Dense Layer  →  SoftMax activation (multi-class output)
```

**Training configuration:**
- Optimizer: Adam
- Loss: Sparse Categorical Cross-Entropy
- Epochs: 50
- Batch size: 32
- Callbacks: EarlyStopping, ReduceLROnPlateau

---

## Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Decision Tree (before tuning) | 80% | — | — | — |
| KNN (before tuning) | 66% | — | — | — |
| LSTM (before tuning) | 100% | 100% | 100% | 100% |
| Decision Tree (after tuning) | 100% | 100% | 100% | 100% |
| KNN (after tuning) | 100% | 100% | 100% | 100% |
| **LSTM (after tuning)** | **100%** | **100%** | **100%** | **100%** |

The LSTM model achieves **perfect accuracy** on test data, significantly outperforming prior systems that report 70–85% accuracy.

---

## Future Work

- Integration of **real-time job market data** for dynamic recommendations
- Expansion to include **postgraduate and professional career paths**
- Deployment as a **web application** for wider student accessibility
- Incorporating **emotional intelligence assessments** for deeper personalization

---

## License

This project is licensed under the [MIT License](LICENSE).
