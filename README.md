# Olist E-Commerce — Product & Category Analysis

Exploratory analysis of a real Brazilian e-commerce dataset,
combining SQL-based data extraction with Python visualization.

## Goal

Identify which product categories drive the most sales, and
whether high-volume categories also deliver high customer
satisfaction. The central question: do the best-selling
categories also have the happiest customers?

## Key Findings

- **Volume and satisfaction don't always align.** The most
  sold categories are not necessarily the best reviewed.
  The scatter plot in Section 6 identifies which categories
  have high demand but low satisfaction — these represent
  the greatest opportunity for business improvement.

- **Poor reviews are largely a logistics problem, not a
  product problem.** There is a statistically significant
  negative correlation between delivery time and review
  score. Orders delivered in 1–7 days average above 4
  stars; orders taking 30+ days drop below 3.5. This
  changes the interpretation of the problem entirely —
  improving delivery times may have more impact than
  improving the products themselves.

- **Volume vs revenue tell different stories.** Some
  categories rank high in units sold but low in revenue
  due to low average prices. A business optimizing for
  revenue should prioritize differently than one
  optimizing for transaction volume.

## Workflow

This project simulates a real-world analytics workflow:
data is loaded from CSVs into a local SQLite database,
business questions are answered with explicit SQL queries,
and results are visualized in Python.

## Limitations

- Data covers 2016–2018 and may not reflect current
  consumer behavior or logistics infrastructure.
- Review scores are biased toward extremes (1s and 5s),
  which can distort category averages.
- The negative correlation between delivery time and
  satisfaction is moderate — many other factors drive
  reviews that this analysis does not capture.
- Causality cannot be established: we cannot determine
  whether poor reviews are caused by slow delivery or
  whether dissatisfied customers are simply more likely
  to leave negative reviews regardless.

## What I Would Add With More Time

- **NLP on review text** to separate complaints about
  delivery from complaints about product quality.
- **Predictive model** to quantify the independent
  contribution of price, category, and delivery time
  on review score.
- **Geographic analysis** to identify which Brazilian
  states have the worst delivery times and how that
  maps to satisfaction.

## Stack

Python · pandas · SQLite · seaborn · matplotlib · scipy

## How to Run
```bash
pip install pandas numpy matplotlib seaborn scipy
jupyter notebook notebooks/olist_analysis.ipynb
```

Update the `DATA_PATH` variable in the second cell to
point to your local copy of the Olist CSV files.
