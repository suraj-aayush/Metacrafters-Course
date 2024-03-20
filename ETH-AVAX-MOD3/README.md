# Arya Token (ARCH) Smart Contract

## Overview

Arya Token (ARCH) is an Ethereum-based ERC-20 token smart contract that provides basic functionalities for minting, burning, and transferring tokens. The contract owner has the exclusive right to mint new tokens.

## Contract Details

- **Name:** Arya Token
- **Symbol:** ARCH
- **Decimals:** 18
- **Total Supply:** Tracks the total supply of the token.

## Smart Contract Functionalities

### Minting

The contract owner can mint new tokens using the `mint` function. Only the contract owner has the authority to mint tokens, providing a secure way to manage the token supply.

solidity
function mint(address to, uint256 amount) public {
    require(msg.sender == owner, "Only the contract owner can mint tokens.");
    require(amount > 0, "Amount must be greater than 0.");

    balances[to] += amount;
    totalSupply += amount;
}

## Burning
Tokens can be burned using the burn function. The owner can reduce the token supply by burning a specified amount of tokens from a particular address.

function burn(address from, uint256 amount) public {
    require(amount <= balances[from], "Amount exceeds balance.");

    balances[from] -= amount;
    totalSupply -= amount;
}
## Transferring
The contract supports the standard ERC-20 token transfer functionality through the transfer function. Users can transfer tokens to another address, provided they have a sufficient balance.
function transfer(address to, uint256 amount) public {
    require(amount <= balances[msg.sender], "Amount exceeds balance.");
    require(to != address(0), "Cannot transfer to the zero address.");

    balances[msg.sender] -= amount;
    balances[to] += amount;
}
## Deployment
To deploy this contract, compile it using a Solidity compiler version compatible with ^0.8.18. After compilation, deploy the contract on an Ethereum-compatible blockchain network.

## License
This smart contract is released under the MIT License. See the LICENSE file for more details.
