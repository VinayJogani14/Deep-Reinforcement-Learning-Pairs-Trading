# Deep-Reinforcement-Learning-Pairs-Trading

This project focuses on applying deep reinforcement learning (DRL) to the financial strategy of pairs trading, a type of market-neutral investment approach. The objective is to develop a machine learning model capable of identifying profitable trading opportunities by monitoring the price relationship (spread) between two correlated assets, in this case, Apple (AAPL) and Microsoft (MSFT). 

### Financial Aspect:
Pairs trading is based on the idea that two historically correlated stocks will eventually revert to their mean spread. When the spread deviates significantly from the norm, a trader can short the outperforming stock and buy the underperforming one, expecting the spread to converge over time. The project implements this concept by tracking the spread (price difference) between the two stocks. It incorporates rolling averages (10-day and 30-day) of the spread to smooth out short-term fluctuations and provide a clearer signal for identifying divergence. Additionally, volatility is measured through rolling standard deviation, which is crucial for understanding risk in the strategy and for making decisions during more turbulent market conditions.

### Technical Aspect:
On the technical side, the project leverages deep reinforcement learning to automate the trading strategy. DRL is a type of machine learning where an agent interacts with an environment (in this case, the stock market), receiving feedback in the form of rewards (profits/losses), and learns to optimize its actions (buy, sell, or hold) over time. The project involves:

1. **Data Preprocessing**: Stock data for both Apple and Microsoft is imported and used to compute the spread, which is the key feature for the DRL agent.
2. **Feature Engineering**: In addition to the raw spread data, rolling averages and volatility are calculated to enhance the dataset. These features help the model make more informed decisions by understanding both the trend and the risk associated with the spread.
3. **Environment Creation**: A custom trading environment is built, where the DRL agent interacts by choosing actions based on current market conditions (spread, moving averages, volatility, etc.). The environment provides feedback to the agent, typically in terms of profits or losses from executed trades, helping it learn which actions are most profitable.
4. **Model Training**: The DRL agent is trained to optimize its trading strategy. As it progresses, it aims to identify optimal points to enter or exit trades by exploiting the mean-reverting behavior of the spread between Apple and Microsoft stocks.

Overall, the project combines financial expertise in pairs trading with advanced technical methods like reinforcement learning to create a robust, automated trading system capable of real-time decision-making in a financial market setting.
