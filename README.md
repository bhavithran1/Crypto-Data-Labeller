# Crypto-Data-Labeller
Uses triple barrier method to label data. Contains a checker to inform the profitability of a trading bot.
<br>

# What is triple barrier method labelling?
<br>
<div align="center">
<img hight="300" width="700" alt="JPG" align="center" src="https://github.com/bhavithran1/bhavithran1/blob/main/assets/trp.jpg">
</div>

<br>
<br>

The idea behind the triple-barrier method is that we have three barriers: an upper barrier, a lower barrier, and a vertical barrier. The upper barrier represents the threshold an observation’s return needs to reach in order to be considered a buying opportunity (a label of 1), the lower barrier represents the threshold an observation’s return needs to reach in order to be considered a selling opportunity (a label of -1), and the vertical barrier represents the amount of time an observation has to reach its given return in either direction before it is given a label of 0.

<br>

# How to use the labeller script above?

<br>

1. Install all the required packages and import them in python
2. Convert your own dataset to parquet format (Saves time and is more space-efficient)
3. Change the path in the labeller script to your own dataset
4. Run labeller-slow  through backtesting.py (This will give more insight but takes a long time)
5. Run labeller-fast for fast coversion of dataset into labels

<br>
<br>
<div align="center">
<img hight="300" width="700" alt="PNG" align="center" src="https://github.com/bhavithran1/bhavithran1/blob/main/assets/triple-result.png">
</div>

<br>
<br>

# How to use the checker script ?

<br>
1. Create a "product.csv" with ohlcv and labels(assuming the labels are from your own trading bot)

```
Open,High,Low,Close,Volume,labels
46368.73,46391.49,46314.26,46331.08,30.45894,0
46331.07,46336.1,46300.0,46321.34,20.96029,0
46321.34,46443.56,46280.0,46436.03,35.86682,0
46436.03,46518.32,46432.5,46518.31,29.31849,0
46518.31,46527.26,46427.06,46427.95,27.81847,0
```

<br>

2. You can use the y.csv file to check the labels distribution

```
labels.to_csv('data/y.csv')
print(labels.value_counts())
labels.value_counts().plot.bar()
```
<br>

<div align="center">
<img hight="300" width="500" alt="PNG" align="center" src="https://github.com/bhavithran1/bhavithran1/blob/main/assets/labels.png">
</div>

<br>

3. Run the backtest function to get the metrics spreadsheet and you can easily evaluate your trading bot's performance
<br>

<div align="center">
<img hight="300" width="300" alt="PNG" align="center" src="https://github.com/bhavithran1/bhavithran1/blob/main/assets/backtest.png">
</div>

<br>
<br>

## Dependencies

- `pandas`
- `backtesting.py`
- `numpy`

<br>
<br>
<br>








