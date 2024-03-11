# Wolverine NFT Collection Smart Contract - Readme

## Overview

Welcome to the readme for the Wolverine NFT Collection Smart Contract. This contract, implemented in Solidity, facilitates the creation and management of a unique NFT collection named "Wolverine." It is based on the ERC-721A standard, an augmented version of the ERC-721 standard, enhancing functionality.

## Contract Features

1. **Minting Functionality:**
   - The contract allows the owner to mint Wolverine-themed NFTs.
   - The maximum number of tokens that can be minted is limited to 5 (`maxQuantity`).

2. **Base URL Configuration:**
   - The base URL for the NFTs is set to "https://gateway.pinata.cloud/ipfs/QmWkzzhkgjMAmFi86TGdEmPtjnomCpA1RndF2si6pvrmYy/".
   - This URL is used to construct the full URI for each NFT.

3. **Owner Privileges:**
   - The contract includes a modifier (`onlyOwner`) to restrict certain functions to the contract owner.

4. **Prompt Description:**
   - A prompt description is provided for the Wolverine NFTs, explaining the inspiration behind the collection.
   - The description is accessible through the `promptDescription` function.

## Getting Started

### Prerequisites

Before working with this smart contract, ensure you have the following installed:

- Solidity Compiler
- Ethereum Wallet (e.g., MetaMask)

### Deployment

1. Deploy the smart contract on the Ethereum blockchain.
2. Set the appropriate permissions and configurations, such as the base URL and maximum quantity.

### Minting NFTs

1. Only the contract owner can mint NFTs using the `mint` function.
2. The `mint` function allows the owner to specify the quantity of NFTs to mint.

### Base URI Configuration

1. The base URI for the NFTs is configured in the `baseUrl` variable.
2. Update the `baseUrl` variable to change the base URL for the NFTs.
