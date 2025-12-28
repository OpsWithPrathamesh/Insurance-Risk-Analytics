Markdown

# The Cognitive Risk Engine: Strategic Insurance Analytics

### A Dual-Module Framework for Corporate Benefits & Reinsurance Optimization

![Project Status](https://img.shields.io/badge/Status-Complete-success)
![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📖 Executive Summary

The **Cognitive Risk Engine** is a strategic data analytics portfolio designed to address the two critical pillars of the modern insurance brokerage model: **Corporate Health (Employee Benefits)** and **Reinsurance Treaty Pricing**.

Moving beyond simple descriptive reporting, this project leverages **Unsupervised Learning (K-Means)** and **Stochastic Modeling (Monte Carlo)** to build a decision-support system. It empowers stakeholders to shift from reactive claims handling to proactive risk mitigation and capital optimization.

---

## 🧠 Strategic Context: The "Proxy Data" Methodology

### ❓ Why utilize "Car Accident" data for a Health Insurance project?

In **Module B (Reinsurance)**, we utilize the *French Motor Third-Party Liability (freMTPL2)* dataset to model catastrophic risk. This is a deliberate strategic choice driven by two factors:

1.  **Data Privacy & Compliance (HIPAA/GDPR):**
    Real-world "Catastrophic Health Claims" data (e.g., organ transplants, late-stage oncology) is highly sensitive and protected by strict privacy laws. Publicly available health datasets often lack the "extreme tail" values necessary for valid reinsurance modeling.

2.  **Mathematical Equivalence (The "Actuarial Twin"):**
    From a statistical perspective, **Motor Liability** and **Catastrophic Health** risks share the exact same mathematical DNA:
    * **High Frequency / Low Severity:** The majority of claims are small (Fender benders $\approx$ Routine OP/Flu shots).
    * **Heavy Tails:** A tiny percentage of claims are massive and can cause ruin (Fatal pile-ups $\approx$ Neonatal ICU/Transplants).

**The Strategy:** By modeling the *freMTPL2* dataset, this project demonstrates the capability to fit **Heavy-Tailed Distributions (Poisson/Lognormal)** and price **Excess-of-Loss Treaties**. The underlying algorithm is domain-agnostic; the code built here can be pointed at proprietary health data in a production environment without logical modification.

---

## 🏗️ Project Architecture

The solution is divided into two distinct analytical modules:

### 🏥 Module A: The Corporate Health Optimizer
* **Objective:** Stratify the employee population to identify hidden cost drivers.
* **Data Source:** Medical Cost Personal Datasets (Kaggle).
* **Technique:** Unsupervised Learning (**K-Means Clustering**).
* **Key Insight:** Identified a **"Critical Red Zone"** (approx. 20% of staff) driven primarily by smoking status, with claims costs **4x higher** than the baseline. This supports the business case for targeted "Smoking Cessation" wellness programs.

### 🛡️ Module B: The Reinsurance Treaty Lab
* **Objective:** Price an "Excess of Loss" (XoL) treaty to protect against bankruptcy.
* **Data Source:** French Motor Third-Party Liability (Actuarial Standard Proxy).
* **Technique:** Stochastic Modeling (**Monte Carlo Simulation** with 1,000 iterations).
* **Key Insight:** Demonstrated how a Retention Limit of **€30,000** effectively "chops off the tail" of the loss distribution, capping the client's volatility and eliminating bankruptcy risk (Probability of Ruin < 0.1%).

---

## 📊 Visuals & Dashboards

The project generates a **Strategic Executive Dashboard** (`Final_Strategic_Dashboard.png`) combining three key views:
1.  **Risk Stratification Pie:** The breakdown of "Red/Yellow/Green" employee risk tiers.
2.  **Cost Driver Analysis:** Bar chart quantifying the financial impact of lifestyle choices (Smoking).
3.  **Capital Protection Histogram:** A "Gross vs. Net" risk distribution showing exactly how the Reinsurance Treaty eliminates tail risk.

---

## ⚙️ Installation & Usage

### Prerequisites
Ensure you have Python 3.8+ installed.

### 1. Clone the Repository
```bash
git clone https://github.com/OpsWithPrathamesh/Insurance-Risk-Analytics.git
cd cognitive-risk-engine

2. Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy


3. Run the Engine
You can run the entire analysis in a single step. The script will ingest data, train models, run simulations, and generate the dashboard.
```bash
python main_risk_engine.py
(Note: Ensure the data/ folder contains insurance.csv, freMTPL2freq.csv, and freMTPL2sev.csv before running.)
