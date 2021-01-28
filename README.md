# hidingbook-api-docs
Integration documentation for the HidingBook. 

The HidingBook is a backend infrastructure component of the Hiding Game which hosts hidden orders only fillable by KeeperDAO keepers. It also supports client friendly APIs which enable a smooth front end user experience.

Integrating a client with the HidingBook enables the client's users to coordinate with KeeperDAO keepers for the capture of MEV (miner extractable value). This is a win-win because both users and keepers are working together to maximize profit generation from a trade the user was going to perform anyways. The profits generated are returned back to the user in $ROOK tokens. The underlying profit token is deposited into a pool controlled by $ROOK holders.

[Client and partner integration guide](docs/client.md)

[API documentation](docs/api.md)

[Keeper integration guide](docs/keeper.md)

### Client use cases
* DEXs
* DEX aggregators
* Wallets
* DeFi products

### User benefits
* Protection against invisible slippage
* Protection against sandwich trading attacks 
* Trade without paying gas
* Get rewarded in $ROOK for user participation in MEV capture, which results in the user trading at a better price than they asked for

### Keeper benefits
* No gas auctions
* Maximized profit opportunities
* No gas tokens required to trade efficiently
* Avoid the mempool front running battles

### Why HidingBook limit orders are better than all open limit orders
* The protocol we're using is more gas efficient than all other limit order protocols on Ethereum
* The keepers filling limit orders source liquidity from all major DEX protocols
* Because orders are fillable only by our keepers, no gas auctions will occur. This means our keepers can also fill your orders at `safe low` and `normal` gas prices instead of only the `fast` and `next block` gas prices you pay on DEX aggregators. This increases the likelihood that the user's order is filled.  It also increases the MEV captured for the user which increases the user's $ROOK reward for making the order
