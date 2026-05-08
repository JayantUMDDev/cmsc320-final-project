# CMSC 320 Final Project — S&P 500 Stock Direction Tutorial

**Author:** Jayant Maheshwari
**Course:** CMSC 320 — Introduction to Data Science (Spring 2026, Dr. Fardina Alam)

A public-facing data-science tutorial that walks through the full pipeline — data
curation → cleaning → exploratory analysis with formal hypothesis tests → feature
engineering → machine learning with class-balanced training, threshold tuning, and
walk-forward cross-validation — to test whether simple technical signals can predict
next-day direction for S&P 500 stocks.

## Live tutorial

**Hosted on GitHub Pages:** https://jayantumddev.github.io/cmsc320-final-project/

The hosted page is the rendered `index.html`. It is the primary deliverable.

## Repository layout

```
FinalProject/
├── CMSC320_Final_Jayant_Maheshwari.ipynb   # the source notebook
├── index.html                               # rendered tutorial (deployed to Pages)
├── figures/                                 # plots saved by the notebook
├── data/archive/                            # CSV inputs (large file gitignored — see below)
├── notebooks/                               # checkpoint-2 EDA artifact
├── requirements.txt                         # pinned Python deps
└── README.md
```

## Reproducing the tutorial locally

```bash
# 1. Clone
git clone https://github.com/JayantUMDDev/cmsc320-final-project.git
cd cmsc320-final-project

# 2. Install dependencies (Python 3.10+)
pip install -r requirements.txt

# 3. Download the dataset
#    The 96 MB sp500_stocks.csv is gitignored because it exceeds GitHub's
#    100 MB single-file limit. Download it from Kaggle:
#       https://www.kaggle.com/datasets/andrewmvd/sp-500-stocks
#    and place all three CSVs at:
#       data/archive/sp500_stocks.csv
#       data/archive/sp500_companies.csv
#       data/archive/sp500_index.csv

# 4. Run the notebook end to end
jupyter nbconvert --to notebook --execute CMSC320_Final_Jayant_Maheshwari.ipynb \
  --output CMSC320_Final_Jayant_Maheshwari.ipynb

# 5. (Optional) regenerate the hosted HTML
jupyter nbconvert --to html CMSC320_Final_Jayant_Maheshwari.ipynb --output index.html
```

## Dataset

**[S&P 500 Stocks (daily updated)](https://www.kaggle.com/datasets/andrewmvd/sp-500-stocks)**
by Andrew MVD on Kaggle, released under the CC0 Public Domain license.
Three CSVs covering 2010–2024: per-stock OHLCV, company metadata, and the index level.

## Headline result

After class-balanced training, threshold tuning, and 5-fold walk-forward
cross-validation, simple technical features (lagged returns, moving-average ratio,
volume ratio, rolling volatility) **do not** beat the naïve "always predict up"
baseline at the broad-market level. A handful of sectors (Real Estate, Industrials,
Communication Services, Healthcare, Basic Materials) show single-basis-point edges;
Financial Services and Technology do not. Read the tutorial for the full walkthrough
and the methodological discipline that produced this honest result.

## License

Code: MIT. Dataset: see Kaggle (CC0). Tutorial prose: © 2026 Jayant Maheshwari.
