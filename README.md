# Market Sentiment Analysis

## Introduction

Financial markets are heavily influenced by investor sentiment, which can drive price movements, volatility, and trading decisions. This project aims to analyze how market sentiment impacts trading performance and behavior using real-world trading and sentiment datasets.

The study focuses on understanding whether traders modify their strategies under different sentiment conditions such as Fear, Greed, Extreme Greed, and Neutral, and how these changes affect profitability and risk.

---

## Objectives

The primary objectives of this analysis are:

- To evaluate the relationship between market sentiment and trading performance (PnL, win rate)
- To analyze behavioral changes in trading under different sentiment conditions
- To identify distinct trader segments based on leverage, activity, and consistency
- To derive actionable trading strategies based on observed patterns

---

## Datasets

### 1. Trading Dataset

This dataset contains detailed trade-level information, including:

- Timestamp
- Account ID
- Trade execution price
- Trade size (tokens and USD)
- Trade direction (Long/Short)
- Closed Profit and Loss (PnL)
- Transaction details

---

### 2. Sentiment Dataset

This dataset includes:

- Timestamp
- Market sentiment classification (Fear, Greed, Extreme Greed, Neutral)

---

## Data Preparation

The following preprocessing steps were performed:

- Loaded both datasets into Pandas DataFrames
- Verified the number of rows and columns
- Checked for missing values and duplicates  
  → No missing values or duplicate records were found
- Converted timestamps into datetime format
- Created a common `date` column for both datasets
- Aligned datasets at a daily level
- Merged datasets using the `date` column

---

## Feature Engineering & Metrics

Several key metrics were created to support analysis:

### Performance Metrics
- Daily PnL per account
- Average PnL per sentiment category
- Win rate (percentage of profitable trades)

### Behavioral Metrics
- Number of trades per day
- Average trade size (USD)
- Long vs Short ratio
- Leverage proxy using position size

### Segmentation Metrics
- Trader frequency (Frequent vs Infrequent)
- Leverage category (High vs Low)
- Consistency (based on PnL variability)

---

## Analysis

### 1. Performance vs Sentiment

The analysis compared average PnL across sentiment categories:

- Fear showed the highest average PnL
- Greed showed moderate returns
- Extreme Greed and Neutral showed lower returns

**Important Note:**  
The number of overlapping sentiment dates is limited, which may affect the statistical reliability of these results.

---

### 2. Behavioral Changes Based on Sentiment

#### Trade Frequency
- Highest trading activity observed during Fear
- Lower activity during Neutral and Extreme Greed

**Interpretation:**  
Traders are more active during volatile or uncertain market conditions.

---

#### Position Size
- Larger position sizes during Fear and Extreme Greed
- Smaller positions during Greed and Neutral

**Interpretation:**  
Traders tend to take larger risks during extreme sentiment conditions.

---

#### Long vs Short Ratio
- Nearly balanced across all sentiment categories

**Interpretation:**  
No strong directional bias is observed in trading decisions.

---

#### Leverage Distribution
- Highest variability during Fear
- Moderate variability during Greed
- Stable behavior during Neutral

**Interpretation:**  
Risk-taking increases significantly during Fear periods.

---

## Segmentation Analysis

### High vs Low Leverage Traders
- High leverage traders show higher average returns
- However, these returns are associated with higher risk

---

### Frequent vs Infrequent Traders
- Frequent traders tend to achieve higher average PnL
- Indicates the importance of active participation

---

### Consistent vs Inconsistent Traders
- Inconsistent traders show higher average returns
- Suggests that higher volatility strategies may yield higher profits

---

## Key Insights

1. Trading activity and position sizes increase during extreme sentiment conditions, indicating higher risk-taking behavior.

2. Leverage variability is highest during Fear periods, highlighting aggressive trading during uncertainty.

3. High leverage and frequent traders generate higher returns, but these returns are associated with increased risk and variability.

---

## Strategy Recommendations

### Strategy 1: Controlled Trading During Fear

During Fear periods, traders should increase participation to take advantage of volatility-driven opportunities, but reduce leverage and position size to manage elevated risk.

---

### Strategy 2: Risk Reduction During Extreme Greed

During Extreme Greed conditions, traders should reduce position sizes and apply stricter risk controls, as markets tend to be overextended and prone to reversals.

---

## Limitations

- Limited number of overlapping sentiment dates
- Small sample size for certain sentiment categories
- Potential impact of outliers on average metrics
- Results may not generalize across all market conditions

---

## Tools & Technologies

- Python
- Pandas
- Matplotlib

---

## Project Structure
