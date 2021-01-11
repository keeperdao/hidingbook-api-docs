# hidingbook-api-docs
API documentation for the HidingBook.  The HidingBook is a backend infrastructure for the Hiding Game which hosts hidden orders only fillable by KeeperDAO keepers. It also supports client friendly APIs to improve the front end user experience.


# General API Information

 * The base endpoint is: `http://18.198.34.146:9999`
 * Example call: [http://18.198.34.146:9999/tokenList](http://18.198.34.146:9999/tokenList)
 * This is under development and will change.
 * All endpoints return either a JSON object or array.



**Get token list**
----
  Returns list of supported tokens.

* **URL**

  /tokenList

* **Method:**

  `GET`

* **Success Response:**

    **Content:** 
```{
  "result": {
    "name": "Hiding Game",
    "timestamp": "2020-12-07T10:35:15+00:00",
    "version": {
      "major": 1,
      "minor": 0,
      "patch": 0
    },
    "keywords": [
      "keeperdao",
      "rook",
      "list"
    ],
    "tokens": [
      {
        "address": "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48",
        "chainId": 1,
        "name": "USDCoin",
        "symbol": "USDC",
        "decimals": 6,
        "logoURI": "https://tokens.1inch.exchange/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48.png"
      },
      {
        "address": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
        "chainId": 1,
        "name": "WrappedEther",
        "symbol": "WETH",
        "decimals": 18,
        "logoURI": "https://tokens.1inch.exchange/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2.png"
      },
      {
        "address": "0x6B175474E89094C44Da98b954EedeAC495271d0F",
        "chainId": 1,
        "name": "DaiStablecoin",
        "symbol": "DAI",
        "decimals": 18,
        "logoURI": "https://tokens.1inch.exchange/0x6b175474e89094c44da98b954eedeac495271d0f.png"
      },
      {
        "address": "0xdAC17F958D2ee523a2206206994597C13D831ec7",
        "chainId": 1,
        "name": "TetherUSD",
        "symbol": "USDT",
        "decimals": 6,
        "logoURI": "https://tokens.1inch.exchange/0xdac17f958d2ee523a2206206994597c13d831ec7.png"
      }
    ],
    "logoURI": "https://miro.medium.com/fit/c/96/96/1*WXMtamzK0_QHWP6dJqFdtA.jpeg"
  },
  "message": "Ok"
}```
 


**Post orders**
----
  Post an array of 0x orders to the orderbook.

* **URL**

  /orders

* **Method:**

  `POST`
  
* **Data Params**

  ```[
  {
    "signature": "0x1caf4e0f3b3c427b30cf584ef0d7e29134445d06784ce82ecdc7d71c54ac74d0a92237d34e69274838a4fece8bb3a39feaf91395a3d6ad0f95529b6ddaac3a161303",
    "senderAddress": "0x0000000000000000000000000000000000000000",
    "makerAddress": "0xca77dc47eec9e1c46c9f541ba0f222e741d6236b",
    "takerAddress": "0x3d71d79c224998e608d03c5ec9b405e7a38505f0",
    "makerFee": "0",
    "takerFee": "0",
    "makerAssetAmount": "469905000000000000",
    "takerAssetAmount": "250000000",
    "makerAssetData": "0xf47261b0000000000000000000000000c02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "takerAssetData": "0xf47261b0000000000000000000000000a0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
    "salt": "1608750663000",
    "exchangeAddress": "0x61935cbdd02287b511119ddb11aeb42f1593b7ef",
    "feeRecipientAddress": "0x0000000000000000000000000000000000000000",
    "expirationTimeSeconds": "1608750983",
    "makerFeeAssetData": "0x",
    "takerFeeAssetData": "0x",
    "chainId": 1
  },
  {
    "signature": "0x1c93c6db6a2ca112bbb976b6e129bfc8c7aa71c2df71fc02df0c87cb9a83e0357b777956c22001b59e35d6936e1fb81430d71a0b522319359944f43e6251d588c203",
    "senderAddress": "0x0000000000000000000000000000000000000000",
    "makerAddress": "0xca77dc47eec9e1c46c9f541ba0f222e741d6236b",
    "takerAddress": "0x3d71d79c224998e608d03c5ec9b405e7a38505f0",
    "makerFee": "0",
    "takerFee": "0",
    "makerAssetAmount": "250000000",
    "takerAssetAmount": "469905000000000000",
    "makerAssetData": "0xf47261b0000000000000000000000000a0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
    "takerAssetData": "0xf47261b0000000000000000000000000c02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "salt": "1608750663000",
    "exchangeAddress": "0x61935cbdd02287b511119ddb11aeb42f1593b7ef",
    "feeRecipientAddress": "0x0000000000000000000000000000000000000000",
    "expirationTimeSeconds": "1608750983",
    "makerFeeAssetData": "0x",
    "takerFeeAssetData": "0x",
    "chainId": 1
  }
]```

* **Success Response:**

    **Content:** `TODO`
 

**Get orders**
----
  Get orders from the orderbook.


* **URL**

  /orders

* **Method:**

  `GET`
  
*  **URL Params**

   **Option 1:**
   `makerAddress=[string]`

   **Option 2 (NOT YET IMPLEMENTED):**
   `makerAssetData=[string]`
   `takerAssetData=[string]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{"orders":[{"orderDataGoesHere":"0x12345",},{"orderDataGoesHere":"0x12345",},],"message":"Ok"}`

* **Sample Call:**

  `/orders?makerAddress=0xca77dc47eec9e1c46c9f541ba0f222e741d6236b`
  `/orders?makerAssetData=0xf47261b0000000000000000000000000a0b86991c6218b36c1d19d4a2e9eb0ce3606eb48&takerAssetData=0xf47261b0000000000000000000000000a0b86991c6218b36c1d19d4a2e9eb0ce3606eb48  TODO ThisDoesNotYetWork`


**Get info**
----
  Get all general info.  TODO This does not yet work.

* **URL**

  /info

* **Method:**

  `GET`

* **Success Response:**

    **Content:** `{ id : 12, name : "Michael Bloom" }`
 
* **Error Response:**

    **Content:** `{ error : "User doesn't exist" }`

