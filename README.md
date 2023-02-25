# SampleTokenizeTSLAstock
Outline of how such a Solidity smart contract could be written to tokenize Tesla stock using a Chainlink Oracle.

To begin with, we need to create a smart contract that will represent the Tesla stock token. This can be done using the ERC-20 token standard. We can start with importing the OpenZeppelin library which provides the standard implementation of the ERC-20 token.

This contract will create a token with the name "Tesla Stock Token" and the symbol "TSLA". It will also mint 1 million tokens and assign them to the contract deployer's address.

Now, we need to fetch the latest price of Tesla stock from a Chainlink Oracle and update the token's price accordingly. We can do this using a function called updateTokenPrice().

In this updated contract, we have added a priceFeed variable of type AggregatorV3Interface which will be used to fetch the latest price of Tesla stock from a Chainlink Oracle. We have also added a updateTokenPrice() function which fetches the latest price from the Oracle and updates the token's price accordingly.

The latestRoundData() function returns several values including the latest price of Tesla stock, which is stored in the price variable. We then convert this price to Wei (the smallest unit of Ether) and divide it by 100 to get the price of one token.

Finally, we have added an internal _setPrice() function which will be called by the updateTokenPrice() function to update the token's price.

Note that in order to use the Chainlink Oracle, we need to provide the address of the Oracle contract in the constructor(). This address can be obtained from the Chainlink documentation.

Once this contract is deployed, anyone can buy and sell Tesla stock tokens using Ether. The price of the tokens will be updated automatically based on the latest price of Tesla stock obtained from the Chainlink Oracle.
