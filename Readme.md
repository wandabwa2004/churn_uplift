# Churn Uplift Modeling & Campaign Selection

This project demonstrates how to use uplift modeling to target customer retention interventions in a banking context. It simulates randomized treatments, builds uplift models, segments customers, and selects the best candidates for a retention campaign—all using a synthetic churn dataset.

---

## Problem Statement

Traditional churn models predict who is likely to leave, but **uplift modeling** goes further:  
It identifies which customers are most likely to change their behavior if targeted with a retention offer.  
This enables smarter, budget-aware marketing—maximizing ROI by focusing on "persuadable" customers.

---

## Workflow Overview

1. **Load and preprocess data:**  
   - Reads a synthetic churn dataset.
   - Engineers features (e.g., tenure).

2. **Temporal train/test split:**  
   - Ensures honest evaluation by splitting on account open date.

3. **Simulate randomized treatment:**  
   - Assigns a random treatment flag and simulates observed outcomes.

4. **Feature selection:**  
   - Auto-detects categorical and numeric features.

5. **Model training:**  
   - Trains separate logistic regression models for treated and control groups.

6. **Score uplift:**  
   - Predicts churn probabilities for both scenarios and computes uplift.

7. **Segment customers:**  
   - Classifies customers into Persuadable, Sure Thing, Lost Cause, Sleeping Dog, and Gray Zone.

8. **Campaign selection:**  
   - Ranks customers by expected profit and selects the best within budget.

9. **Save results:**  
   - Outputs scored test set and campaign selection list as CSV files.

---

## How to Run

1. **Clone the repository:**
    ```bash
    git clone https://github.com/wandabwa2004/churn_uplift.git
    cd py
    ```

2. **Install dependencies:**
    ```bash
    pip install numpy pandas scikit-learn matplotlib
    ```

3. **Run the notebook:**
    - Open `uplift_analysis.ipynb` in Jupyter or VS Code.
    - Run all cells.

    *(Make sure the dataset path in the notebook matches your local setup.)*

---

## Outputs

- `test_uplift_scored.csv` — scored test set with uplift predictions and segments.
- `campaign_selection.csv` — top customers to target, ranked by expected profit.

---

## Key Concepts

- **Uplift Modeling:** Predicts the incremental effect of a treatment (e.g., retention offer) on individual customer behavior.
- **Customer Segmentation:**  
    - *Persuadable*: Most likely to respond positively to treatment.
    - *Sure Thing*: Would stay anyway.
    - *Lost Cause*: Unlikely to respond.
    - *Sleeping Dog*: May react negatively.
    - *Gray Zone*: Uncertain effect. Experiment further with this segment.

- **Budget-aware selection:** Maximizes campaign ROI by considering both uplift and cost.


---

**Note:**  
This project uses synthetic data for demonstration and educational purposes only.
