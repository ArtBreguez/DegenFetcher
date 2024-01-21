# DegenFetcher

Easily get historical data from Chainlink feeds
 
## About DegenFetcher
 
DegenFetcher is a Solidity smart contract that serves as a bridge between conventional timestamps (e.g. "Aug 6, 2020, 12:00am") and Chainlink round IDs. While Chainlink doesn't natively support fetching historical data by timestamp, DegenFetcher bridges this gap. It uses a binary search algorithm to repeatedly fetching timestamps for various round IDs from a Chainlink aggregator. When it's identified the correct rounds of Chainlink data, it culls the data to the desired density; e.g. one price point every 30 minutes.

DegenFetcher accepts the following parameters:
* Starting timestamp
* Duration (e.g. 1 day)
* Density (e.g. 48 data points per day)
* Address of any [Chainlink feed](https://medium.com/r?url=https%3A%2F%2Fdocs.chain.link%2Fdocs%2Fethereum-addresses%2F); e.g. ETH/USD, DOGE/USD, EUR/USD


## Deployment & Verify

```
truffle migrate --network mumbai
truffle run verify DegenFetcher --network mumba
```