# Trade GPT

This repository contains the code for the Trade GPT forex robot developed by the Forex Robot Easy Team. 

For detailed reviews and trading results of this product, please visit [forexroboteasy.com](https://forexroboteasy.com/forex-robot-review/tradegpt-review-unveiling-a-full-cycle-forex-software/).

## Description

Trade GPT is an automated forex trading system that uses a combination of moving averages and predefined patterns to identify potential trading opportunities. The robot searches for opportunities based on the specified search period, entry criteria, and exit criteria.

### Input Parameters

- `searchPeriod` (default: 20): The period for searching potential trading opportunities.
- `entryCriteria` (default: 0.5): The threshold for entry conditions.
- `exitCriteria` (default: 0.2): The threshold for exit conditions.

### Global Variables

- `ticket`: The order ticket.
- `isTradeOpen`: A flag to indicate if a trade is open.
- `isExitCriteriaMet`: A flag to indicate if exit criteria is met.

### Libraries Used

- `Trade`: A library for executing trades.
- `MovingAverages`: A library for calculating moving averages.

## How it Works

The Trade GPT robot follows a simple trading strategy. On each tick, it checks if a trade is open. If a trade is open, it checks if the exit criteria is met and closes the trade if necessary. If no trade is open, it searches for potential trading opportunities based on the predefined patterns and executes a trade if the conditions are met.

The `OnInit()` function initializes the trading system by setting the trade execution mode to instant.

The `OnTick()` function is called on each tick and contains the main trading logic. It first checks if a trade is open. If a trade is open, it checks if the exit criteria is met and closes the trade if necessary. If no trade is open, it calls the `SearchOpportunities()` function to search for potential trading opportunities. If a potential trading opportunity is found, it calls the `ExecuteTrade()` function to execute the trade.

The `SearchOpportunities()` function calculates the Simple Moving Average (SMA) values for the specified period using the `MovingAverages` library. It then calculates the GPT value by averaging the SMA values. If the GPT value is greater than the entry criteria, it returns true indicating a potential trading opportunity is found.

The `ExecuteTrade()` function checks the predefined patterns for buy and sell decisions using the `CheckBuyPattern()` and `CheckSellPattern()` functions respectively. If the buy decision is true, it opens a buy trade using the `Buy()` function from the `Trade` library. If the sell decision is true, it opens a sell trade using the `Sell()` function.

The `CheckBuyPattern()` and `CheckSellPattern()` functions are placeholders for implementing the predefined patterns for buy and sell decisions. Currently, they return false indicating that no buy or sell decision is made.

The `OnTrade()` function is called when a trade event occurs. It checks if the trade is closed by comparing the position close time. If the trade is closed, it sets the exit criteria flag to true.

Please note that ForexRobotEasy is not the official developer of this product. This code is provided as a sample that can work as described in the product. To find the official developer of this product, please use the MQL5 platform.
