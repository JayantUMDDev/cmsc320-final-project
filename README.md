# cmsc320-final-project

CMSC 320 (Spring 2026) Final Project / Tutorial  
Jayant Maheshwari

## Dataset (Kaggle)
**S&P 500 Stocks (daily updated)**  
Source: https://www.kaggle.com/datasets/andrewmvd/sp-500-stocks

This dataset includes daily historical stock data for S&P 500 constituents, an S&P 500 index file, and company metadata (e.g., sector/industry). This dataset is large enough for analysis because it includes daily data across hundreds of S&P 500 stocks over many trading days, which gives plenty of observations for exploration, hypothesis testing, and machine learning.

## Why this dataset
I chose this dataset because it lines up with my interest in computational finance, and because finance is one of those areas where small improvements can actually matter in real money and real risk. The stock market is a complex system where news, human behavior, and bigger economic trends all mix together, which makes it a really interesting space to analyze with data.

I’ve been into the stock market ever since I first got introduced to investing in high school. Back then, a lot of the “rule of thumb” ideas I heard were things like trading volume and simple moving averages, like comparing shorter-term and longer-term averages to guess momentum. For this project, I want to test whether those kinds of signals actually show anything useful when you evaluate them fairly, and whether they can work well as model features. I’m also interested in what other strong signals people use, and whether a simple model can beat basic benchmarks like buy-and-hold on the S&P 500 when you test it in a realistic way.

## Draft research questions
- If I build a simple model using past returns, volume, and moving-average features, does it beat basic baselines like “always predict up” or buy-and-hold on the S&P 500?
- Are some sectors easier to model than others, or do these signals work better in certain sectors (like tech vs utilities)?
- When a model does well in one time period, does it still work later, or does the market “change the rules” over time?