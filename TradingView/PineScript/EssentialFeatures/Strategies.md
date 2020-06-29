[User Manual](/TradingView/PineScript.md) > [Essential features](/TradingView/PineScript/EssentialFeatures.md) > Strategies

# [Strategies](https://www.tradingview.com/pine-script-docs/en/v4/essential/Strategies.html) ストラテジー

- A simple strategy example シンプルなストラテジー例
- Applying a strategy to a chart チャートにストラテジーを適用する
- Backtesting and forwardtesting バックテスト＆フォワードテスト
- Broker emulator ブローカーエミュレーター
- Order placement commands
- Closing market position
- OCA groups
- Risk management
- Currency

A strategy is a Pine script that can send, modify and cancel buy/sell orders. Strategies allow you to perform backtesting (emulation of a strategy trading on historical data) and forwardtesting (emulation of a strategy trading on real-time data) according to your algorithms.

A strategy written in Pine has many of the same capabilities as a Pine study, a.k.a. indicator. When you write a strategy, it must start with the strategy annotation call (instead of study). Strategies may plot data, but they can also place, modify and cancel orders. They also have access to essential strategy performance information through specific keywords. The same information is available externally in the Strategy Tester tab. Once a strategy is calculated on historical data, you can see hypothetical order fills.

## A simple strategy example シンプルなストラテジー例

```
//@version=4
strategy("test")
if bar_index > 4000
    strategy.entry("buy", strategy.long, 10, when=strategy.position_size <= 0)
    strategy.entry("sell", strategy.short, 10, when=strategy.position_size > 0)
plot(strategy.equity)
```
