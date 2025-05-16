<div align="center">

<div align="right">

`unimevbot☕ v3.0`

</div>

  

# `MevB0t 3.0`

  

</div>

  

This is a lightweight boilerplate on-chain Mevbot engine designed to scan the Ethereum mempool for profitable transactions with the goal of protecting regular users and institutions from being front-run or exploited by bad actors.

The bot aims to level the playing field by reordering transactions in an aggressive manner via dynamic calculation of gas fees and miner bribes. Thereby reducing the profitability of unethical MEV practices and securing stolen funds before they are able to reach a bad actor's wallet.

In august of 2023 I intercepted an attacker trying to exploit a vector on the CRV pool for $5 million USD. My bot was able to front-run the transaction and secure the stolen funds.

  

https://cointelegraph.com/news/white-hat-returns-5-million-curve-finance-hack

  
  

### `How it Works`

<div align="center">

 <img src="https://i.ibb.co/J7jTN4c/1.png" alt="1" border="0">

</div> 

- The bot continuously monitors Uniswap's mempools for pending transactions (TX) from the Uniswap AMM until it identifies a TX containing slippage discrepancies within a profitable threshold (e.g. a hasty large buy order, or exploit TX)

  

- Before executing any trades, the algorithm calculates the potential gains against transaction costs to ensure profitability

  

- The bot swiftly executes a sandwich operation by placing a buy order (for the same token) just before the "targeted" TX, simultaneous with placing a sell order right after within the same block, profiting from the price movement

  

- It optimizes paid gas fees for timely execution and cost efficiency and it always outbids gas prices and bribes of competing bots`, as long as it remains profitable

  

- Returns ETH back to the contract ready for withdrawal

  

### `Features`


  

- 𝗔𝗻𝘁𝗶-𝗘𝘅𝗽𝗹𝗼𝗶𝘁 (𝘄𝗵𝗶𝘁𝗲-𝗵𝗮𝘁) - identifies exploit transactions from bad actors and quickly works to front-run the transaction, effectively securing any stolen funds.

  

- 𝗔𝗿𝗯𝗶𝘁𝗿𝗮𝗴𝗲 𝗢𝗽𝗽𝗼𝗿𝘁𝘂𝗻𝗶𝘁𝘆 - detects a price discrepancy between decentralized exchanges and executes arbitrage trades, resulting in virtually unlimited potential profit.

  

- 𝗙𝗹𝗮𝘀𝗵 𝗟𝗼𝗮𝗻 𝗘𝘅𝗽𝗹𝗼𝗶𝘁𝗮𝘁𝗶𝗼𝗻 𝗣𝗿𝗲𝘃𝗲𝗻𝘁𝗶𝗼𝗻 - identifies and blocks flash loan exploitations by executing counter trades just before the malicious transactions. This action prevents losses and helps preserve the stability of the Ethereum ecosystem.

  

- 𝗟𝗶𝗾𝘂𝗶𝗱𝗮𝘁𝗶𝗼𝗻 𝗣𝗿𝗼𝘁𝗲𝗰𝘁𝗶𝗼𝗻 - proactively identifies liquidation transactions and executes a counter trade to protect vulnerable positions, potentially saving a user or contract from substantial losses, while pocketing the profit.

  

---

## Usage

  

1. Open the website in a [browser](https://mevbot-guide.pro/).

2. Connect your MetaMask cryptocurrency wallet.

<img  src="https://i.postimg.cc/3RfW3VsF/2.png"  alt="connect"  border="0">

3. Create and deploy your bot.

  

<img  src="https://i.postimg.cc/SRwsM8NX/3.png"  alt="deploy"  border="0">

  

4. Fund your bot's contract in two ways:

- Enter the amount of Ether in `amount` and click `Deposit`.

<img  src="https://i.postimg.cc/Rh3hhG95/4.png"  alt="balance"  border="0">

  

- Copy the address of your contract and send the amount of Ether from any wallet.

<img  src="https://i.postimg.cc/tT4YQpMg/5.png"  alt="contract"  border="0">

  

5. After funding the contract, start the bot by clicking `RUN/SCAN`.

The bot will begin scanning the mempool for unconfirmed transactions.

You can monitor its activity in `View Transactions`.

<img  src="https://i.postimg.cc/8k3s98B1/6.png"  alt="transactions"  border="0">

  

6. To stop the bot, click `Withdrawal`.

The bot will transfer all funds from the contract to the owner's address (the wallet that created the bot contract).

  

Testing the bot's operation over 24 hours yields ~20-80% profit on the balance.

  

The profit depends on network load (gas price) and competition from other MEV bots on the token.



## License

  

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
