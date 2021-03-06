# **A module for a bot trading the virtual currency**
##### _Tested on Python 2.7.12_
##### Very thanks to [s4w3d0ff](https://github.com/s4w3d0ff) and [python-poloniex](https://github.com/s4w3d0ff/python-poloniex)

### Features:
- predictionprice module is a set of tools for making a bot that trade virtual currency automatically according to the prediction with the machine learning.
- You can do mainly the followings by using this module.
  - To get the price of virtual currency from Poloniex.com
  - Prediction if the tomorrow's virtual currency price rise or fall by machine learning decision tree algorithm using the scikit-learn.
  - Implementation of the back test.
  - Optimization of the number of the features and training samples.
    - The features are represented with the sequencial past prices.
    - The training sample is a set of the features.
  - Implementation of the market trade with accessing to Poloniex.com in accordance with the predicted buying and selling signs.
  - Function to inform the results of the prediction and the trading by e-mail.

### Prerequired:
- [poloniex(An API wrapper for Poloniex.com written in Python)](https://github.com/s4w3d0ff/python-poloniex)==0.2.2
  - poloniex-0.2.2 will be installed automatically when you install predictionprice module.
- An account of Poloniex.com
- APIKey and Secret to access to Poloniex.com with API.
- A gmail account.

### Install:
```
git clone https://github.com/darden1/python-predictionprice.git
cd python-predictionprice
python setup.py install
```

### Uninstall:
```
pip uninstall predictionprice
```

### Usage:
- Examples of auto trading bot have already prepared.
- The bot executes followings one time a day.
  - Back test.
  - Prediction the virtual currency tomorrow price will rise or fall.
  - Trading with market price in accordance with the prediction.
  - Optimization of the number of the features and training samples.(Optimized learning parameters are used for next day prediction)
  - Sending e-mail to inform the results of the execution.
- Bots are in examples folder.
  - examples/exchangetrade/exchangetradebot.py is for exchange trade.
  - examples/margintrade/margintradebot.py is for margin trade.
    - Remark to transfer fund to margin account when you use margintradebot.py.
- Open exchangetradebot.py or margintradebot.py and set your gmail address, password, poloniex.com APIKey and Secret.
- Run this script with nohup as following.
```
nohup python exchangetradebot.py > out.log 2> err.log &
or
nohup python margintradebot.py > out.log 2> err.log &
```
- You can check the process ID as following when you want to kill the process.
```
ps auxw | grep python
```
- You can change the combination of the currency pair you want to trade with `coins` and `basicCoin`.

###  Caution:
- It is **not absolutely guaranteed** to increase your assets by using this bot.
- I hope if this could help you to create a much better one than this bot. (I would be very happy if you would tell me the new algorithm of the bot when you could achieve it.)
