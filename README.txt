REMIX DEFAULT WORKSPACE

This code defines two contracts:

1. Cryptos (ERC20 Token):

This contract implements the ERC20 standard, a common interface for tokens on the Ethereum blockchain. 
It defines functionalities for:

Specifying token details like name, symbol, and decimals.
Tracking the total token supply (initially set to 1,000,000 in this example).
Storing balances for each address in a balances mapping.
Managing allowances for spending tokens on behalf of others using an allowed mapping.

It implements the required ERC20 functions:

balanceOf: Returns the token balance of an address.
transfer: Transfers tokens from the sender to another address.
allowance: Checks the spender's allowance for a specific address.
approve: Allows another address to spend a specific amount of tokens on the owner's behalf.
transferFrom: Transfers tokens from one address to another using a spender's allowance.

2. CryptosICO (Initial Coin Offering):

This contract inherits from the Cryptos contract and adds functionalities for conducting an ICO (Initial Coin Offering):

Defines variables for the ICO administrator (admin), deposit address (deposit), token price, hard cap (maximum amount to raise), raised amount, sale duration, and minimum/maximum investment limits.
Uses an enum called State to track the ICO's current stage (before start, running, after end, or halted).
Provides functions for:
Halting and resuming the ICO (only accessible by the admin).
Changing the deposit address (only accessible by the admin).
Getting the current ICO state.
Investing in the ICO:
Checks if the ICO is running and within investment limits.
Calculates the number of tokens based on the investment amount.
Transfers tokens from the founder to the investor and ETH to the deposit address.
Emits an Invest event.
Overriding the transfer and transferFrom functions to prevent transfers before the token trade start date.
Burning any remaining tokens held by the founder after the ICO ends.

Overall, this code demonstrates how smart contracts can be used to create and manage tokenized assets with functionalities for conducting an ICO.