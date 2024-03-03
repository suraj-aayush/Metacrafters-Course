# Project Title

ETH + AVAX PROOF: Intermediate EVM Course

## Description

This is a simple contract that was programmed just to check that whether the owner of the contract is the same as one using the contract or not. For this, we used three error methods- require(), revert(), and assert() and all these three functions are performing the same job. 

## Getting Started

### Installing

* How/where to download your program
* Any modifications needed to be made to files/folders

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:
```
pragma solidity ^0.8.18;

contract OwnershipContract {
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    function onlyOwner() public view {
        require(msg.sender == owner, "Only the owner can call this function.");
    }

    function onwerHere() public view {
        if(msg.sender!= owner){
            revert("The caller is not the owner.");
        }
    }

    function Owner() public view {
        assert(msg.sender == owner);
    }
}

```


## Authors

This program has been done by Aayush Kumar
 [Contact me](mailto:210211200@geu.ac.in)



## License

This project is licensed under the MIT License - see the LICENSE.md file for details
