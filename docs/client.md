# Client integration guide

The HidingBook requires the following integration components

 * 0xv4 integration
 * Wallet providers of your choice
    * MetaMask, Ledger, etc
 * A user interface for user input
    * tokenIn, tokenOut
    * order expiration
    * price
 * A user interface for displaying orders
    * view open orders
    * cancel orders
    * view historic orders

#### When the user arrivesUse on the trading screen
Make a call to the `/info` endpoint to get the information you need to initialize the trading screen. The response contains useful information like supported tokens and data needed to sign orders. 

#### When the user is ready to sign an order
Combine the user inputted information along with the properties from the `/info` endpoint to create a valid 0xv4 order.

https://0xprotocol.readthedocs.io/en/latest/basics/orders.html?highlight=txOrigin#rfq-orders

#### When you're ready to submit a signed order
Make a call to the `POST /orders` endpoint to post the order to the HidingBook for validation. The server will alert you of any errors, insufficient balances, or insufficient allowances.

#### When the user is to approve allowances
Allowances are to be made where the spender is the 0xv4 `verifyingContract` provided in the `/info` endpoint.  

#### When the user wants to view orders
Make a call to the `GET /orders` endpoint to get the user's orders. Specify the user's address as the maker. From there you can display them on the screen, present state and fill % information, and give the user the option to cancel an order. The order's status corresponds with 0x's `enum OrderStatus`

https://0xprotocol.readthedocs.io/en/latest/basics/functions.html?highlight=fill%20state#getrfqorderinfo

#### When the user wants to cancel an order
https://0xprotocol.readthedocs.io/en/latest/basics/functions.html?highlight=registerAllowedRfqOrigins#cancelrfqorder

#### 0xv4 Audits
https://0xprotocol.readthedocs.io/en/latest/additional/audits.html

#### 0xv4 javascript can be found on https://www.npmjs.com/
    * '@0x/protocol-utils';
    * '@0x/utils';
    * '@0x/subproviders';
    * '@0x/order-utils';
    * '@0x/contract-addresses';
