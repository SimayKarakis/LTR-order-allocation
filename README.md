
# AI Integration in Spare Parts Order Allocation Planning

This repository contains the notebook and visual outputs for a machine learning project conducted during a summer internship at **Ford Otosan Otomotiv A.Ş.**, within the Digital Products and Services (DPS) department, specifically under the SPIDS (Spare Parts Interactive Distribution Systems) team. The goal was to enhance the existing rule-based order allocation system by developing a more intelligent, data-driven prioritization model using Learning-to-Rank (LTR) methodology.



## Project Objective

> When multiple customer orders compete for limited inventory of a spare part, which orders should be fulfilled first?  
> This project seeks to answer that question by learning prioritization logic from historical data using supervised machine learning.

Key goals:
- Investigate AI integration opportunities in logistics and order planning
- Replace static rules with adaptable ranking based on historical decisions
- Demonstrate model feasibility through training and evaluation of a prototype



## 📂 Repository Structure

```
.
├── LTR_clean.ipynb                   # Main notebook containing all modeling steps
├── Feature_Importance_LTR_Model.png  # Visual output showing top-ranking features
├── Urgent_Order_Ratio_by_Month.png   # Visual showing seasonal urgency trends
├── requirements.txt                  # Python dependencies used in the notebook
└── README.md
```



## 🔧 Tools & Libraries Used

- Python 3.9+
- LightGBM (ranking objective)
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook



## Model Training & Evaluation

- LTR model trained using **LightGBM** with pairwise ranking objective
- Early stopping after 50 rounds with best iteration at 250
- Train/validation/test split: 70/15/15

### ✅ Final NDCG Scores (Test Set)

| Metric   | Score    |
|----------|----------|
| NDCG@1   | 94.97%   |
| NDCG@3   | 93.27%   |
| NDCG@5   | 94.62%   |
| NDCG@10  | 95.87%   |



## 📊 Key Insights

- **Feature Importance**
  - Order Age: 56.1%
  - Order Quantity: 18.6%
  - Rule-Based Priority: 12.5%
  - Hour of Day, Order Type, Dealer Type, Day of Week (combined minor contribution)

- **Ranking Shift Analysis**
  - 99.2% of ranked parts changed position under LTR model vs. rule-based logic
  - Average reordering depth: 3.47 positions

- **Temporal Dynamics**
  - Highest urgent order ratios in Months 8 (15.4%) and 9 (16.4%)
  - Suggests seasonal demand or campaign-driven priorities



## 📁 How to Use

1. Clone the repository:
```bash
git clone https://github.com/SimayKarakis/LTR-order-allocation.git
cd LTR-order-allocation
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Launch the notebook:
```bash
jupyter notebook LTR_clean.ipynb
```



## Academic Context

This project was developed as part of the **CS395 Summer Internship Course** at **Sabancı University**, under the supervision of the SPIDS TechEagles team at Ford Otosan. The goal was to apply machine learning techniques to solve real-world prioritization problems in spare parts logistics.



## License & Disclaimer

This repository is intended for educational and demonstrative purposes only.  
It does not reflect any live deployment or production usage by Ford Otosan.  
All data used in this project was internally shared for academic research within the scope of the internship.
