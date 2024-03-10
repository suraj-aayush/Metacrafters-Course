# ETH + AVAX 
This is the solution to one of the eth + avax module 3.

## Description

In this file, a smart contract was created and compiled using Local Hardhat network. In this contract, we create our own token and use different functions such as mint fucntion which can be used by the owner only, burn and transfer function can be used by any of the user. The contract has been tested and deployed using Remix IDE. The functionalities of the contract has been explained in this Loom video  https://www.loom.com/share/caffd989cb684a30b372da2f987c99e5?sid=4b2ca029-46d9-4d15-93ba-85a27d4aa4f6

## Getting Started

### Executing program

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract Token {

  uint256 public totalSupply;
  address public owner;
  string public name = "BlackRock";
    string public symbol = "BLRK";
    uint8 public decimals = 18;

  constructor() {
    owner = msg.sender;
  }

  mapping(address => uint256) public balances;

  // Mint function
  function mint(address to, uint256 amount) public {
    require(msg.sender == owner, "Only the contract owner can mint tokens.");
    require(amount > 0, "Amount must be greater than 0.");

    balances[to] += amount;
    totalSupply += amount;
  }

  // Burn function
  function burn(address from, uint256 amount) public {
    require(amount <= balances[from], "Amount exceeds balance.");

    balances[from] -= amount;
    totalSupply -= amount;
  }

  // Transfer function
  function transfer(address to, uint256 amount) public {
    require(amount <= balances[msg.sender], "Amount exceeds balance.");
    require(to != address(0), "Cannot transfer to the zero address.");

    balances[msg.sender] -= amount;
    balances[to] += amount;
  }
}
```

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar.
This is deployed using HardHat Compiler and connected to all the other files in the VS Code as shown in the video

## Authors

Contributors names and contact info

Aayush Kumar  
mail: 210211200@geu.ac.in


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
