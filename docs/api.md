# General API Information
 * The base endpoint is: `http://18.198.34.146:9999/v1/`
 * Example call: [http://18.198.34.146:9999/v1/info](http://18.198.34.146:9999/v1/info)
 * We're now using 0xv4 RFQ orders, 0xv3 calls will no longer work.
 * This is under development and will change.
 * All endpoints return either JSON or an array of JSON.


**Get info**
----
  Returns all general information needed to populate the user interface.

* **URL**

  /info

* **Method:**

  `GET`

* **Success Response:**

    ```
    {
      "result": {
        "orderDetails": {
          "verifyingContract": "0xdef1c0ded9bec7f1a1670819833240f027b25eff",
          "chainId": 1,
          "txOrigin": "0xbd49a97300e10325c78d6b4ec864af31623bb5dd",
          "taker": "0x0000000000000000000000000000000000000000",
          "pool": "0x0000000000000000000000000000000000000000000000000000000000000017"
        },
        "tokenList": {
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
        "recommendedMinTradeAmounts": {
          "TODO": 1337
        }
      },
      "message": "Ok"
    }
    ```
  
  
**Get token list**
----
  Returns list of supported tokens.

* **URL**

  /tokenList

* **Method:**

  `GET`

* **Success Response:**

    ```
    {
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
    }
    ```



**Post orders**
----
  Post an array of 0x orders to the orderbook.

* **URL**

  /orders

* **Method:**

  `POST`
  
* **Data Params**

    ```
    [
      {
        'maker': '0xca77dc47eec9e1c46c9f541ba0f222e741d6236b',
        'taker': '0x0000000000000000000000000000000000000000',
        'makerAmount': '93981000000000000',
        'takerAmount': '50000000',
        'makerToken': '0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2',
        'takerToken': '0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48',
        'salt': '1611073656000',
        'expiry': '1611074656',
        'chainId': 1,
        'txOrigin': '0xbd49a97300e10325c78d6b4ec864af31623bb5dd',
        'pool': '0x0000000000000000000000000000000000000000000000000000000000000017',
        'verifyingContract': '0xdef1c0ded9bec7f1a1670819833240f027b25eff',
        'signature': {
          'signatureType': 3,
          'v': 28,
          'r': '0x6a3182de881d03f216bdcbbc5d78c3c1b86b19c880eef7b1f5cde26cc202a142',
          's': '0x7c68df85de87098c97110515a64f27b9c0ff918abfeed375700d7df653f88ee7'
        }
      },
      {
        'maker': '0xca77dc47eec9e1c46c9f541ba0f222e741d6236b',
        'taker': '0x0000000000000000000000000000000000000000',
        'makerAmount': '50000000',
        'takerAmount': '93981000000000000',
        'makerToken': '0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48',
        'takerToken': '0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2',
        'salt': '1611073656000',
        'expiry': '1611074656',
        'chainId': 1,
        'txOrigin': '0xbd49a97300e10325c78d6b4ec864af31623bb5dd',
        'pool': '0x0000000000000000000000000000000000000000000000000000000000000017',
        'verifyingContract': '0xdef1c0ded9bec7f1a1670819833240f027b25eff',
        'signature': {
          'signatureType': 3,
          'v': 28,
          'r': '0x21dc310bff19f899781a70b52940aee98eaa4dcfaee89274de3e300ca716f9f8',
          's': '0x40967fc8ba28e0eff8c707521e9a81ab396a8b55bda88c3f07aad4ae5da584dd'
        }
      }
    ]
    ```

* **Success Response:**

    ```
    {
      'result': {
        'hashList': [
          '0x345cfe65093ee90aec8824be4b7c24070cf56240e04b6fb6e5b1e003f24527f9',
          '0xeb49fb338838615720dd8423650df146db7b1e6408f747733ff01b11383a91a8'
        ]
      },
      'message': 'Order creation succeeded'
    }  
    ```
 

**Get orders**
----
  Get orders from the orderbook.


* **URL**

  /orders

* **Method:**

  `GET`
  
*  **URL Params**

   **Option 1:**
   `maker=[string]`

   **Option 2 (NOT YET IMPLEMENTED):**
   `makerToken=[string]`
   `takerToken=[string]`

* **Sample Call:**
  `/orders?maker=0xca77dc47eec9e1c46c9f541ba0f222e741d6236b`
  
* **Success Response:**

    ```
    {
      "orders": [
        {
          "order": {
            "maker": "0xca77dc47eec9e1c46c9f541ba0f222e741d6236b",
            "taker": "0x0000000000000000000000000000000000000000",
            "makerAmount": "25000000",
            "takerAmount": "46990500000000000",
            "makerToken": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "takerToken": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
            "salt": "1611000201000",
            "expiry": "1611001201",
            "chainId": 1,
            "txOrigin": "0xbd49a97300e10325c78d6b4ec864af31623bb5dd",
            "pool": "0x0000000000000000000000000000000000000000000000000000000000000017",
            "verifyingContract": "0xdef1c0ded9bec7f1a1670819833240f027b25eff",
            "signature": {
              "signatureType": 3,
              "v": 28,
              "r": "0xc6e19b108ca4d059d2999e8011237f7a73a4b034993bc4256ab9bc8e6dddf220",
              "s": "0x1f2fd0d9ccb5e022b1f51dd0ad76695ebabdcfbb276aa3b2d306dd1952ca9531"
            }
          },
          "metaData": {
            "orderHash": "0xd505bf04b6cd3efe0c71568441b639cc1767af04480040933fa67b73a4e317f5",
            "makerBalance_makerToken": 1047850867,
            "makerAllowance_makerToken": 115792089237316195423570985008687907853269984665640564039457584007913129634083,
            "status": 4,
            "filledAmount_takerToken": 0,
            "remainingFillableAmount_takerToken": 0
          }
        },
        {
          "order": {
            "maker": "0xca77dc47eec9e1c46c9f541ba0f222e741d6236b",
            "taker": "0x0000000000000000000000000000000000000000",
            "makerAmount": "50000000",
            "takerAmount": "93981000000000000",
            "makerToken": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "takerToken": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
            "salt": "1611073656000",
            "expiry": "1611074656",
            "chainId": 1,
            "txOrigin": "0xbd49a97300e10325c78d6b4ec864af31623bb5dd",
            "pool": "0x0000000000000000000000000000000000000000000000000000000000000017",
            "verifyingContract": "0xdef1c0ded9bec7f1a1670819833240f027b25eff",
            "signature": {
              "signatureType": 3,
              "v": 28,
              "r": "0x21dc310bff19f899781a70b52940aee98eaa4dcfaee89274de3e300ca716f9f8",
              "s": "0x40967fc8ba28e0eff8c707521e9a81ab396a8b55bda88c3f07aad4ae5da584dd"
            }
          },
          "metaData": {
            "orderHash": "0xeb49fb338838615720dd8423650df146db7b1e6408f747733ff01b11383a91a8",
            "makerBalance_makerToken": 1121680797,
            "makerAllowance_makerToken": 115792089237316195423570985008687907853269984665640564039457584007913129634083,
            "status": 1,
            "filledAmount_takerToken": 0,
            "remainingFillableAmount_takerToken": 93981000000000000
          }
        },
        {
          "order": {
            "maker": "0xca77dc47eec9e1c46c9f541ba0f222e741d6236b",
            "taker": "0x0000000000000000000000000000000000000000",
            "makerAmount": "25000000",
            "takerAmount": "46990500000000000",
            "makerToken": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "takerToken": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
            "salt": "1610994465000",
            "expiry": "1610995465",
            "chainId": 1,
            "txOrigin": "0xbd49a97300e10325c78d6b4ec864af31623bb5dd",
            "pool": "0x0000000000000000000000000000000000000000000000000000000000000017",
            "verifyingContract": "0xdef1c0ded9bec7f1a1670819833240f027b25eff",
            "signature": {
              "signatureType": 3,
              "v": 27,
              "r": "0x5ba37acf248a3b210d52fb89602e27e3ab0020d4ccba3ed131f9ed8db9292884",
              "s": "0x684a65e09e1edf2347d7a34837c4b85d0df49be415159c71c2ad07252113c08c"
            }
          },
          "metaData": {
            "orderHash": "0x62521dcb7c3dc153e9ef7fb2d1ae4df955cacf369f381c4547578b8e316030dc",
            "makerBalance_makerToken": 1047850867,
            "makerAllowance_makerToken": 115792089237316195423570985008687907853269984665640564039457584007913129634083,
            "status": 4,
            "filledAmount_takerToken": 0,
            "remainingFillableAmount_takerToken": 0
          }
        }
      ],
      "message": "Ok"
    }  
    ```
