# Phoenix

This Solidity program is a simple program that demonstrates how tokens work. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how token it works.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.

The contract have three public variables named as tokenName [a string that stores token name], tokenAbbrv [a string that stores token name abrreviation] and totalSupply [an unsigned integer that stores total supply]. It has a single mapping variable named as balances which stores wallet addres a key and no of tokens as value. 

It have two functions named as "burn" and "mint". The mint function takes two parameters "address of wallet" and "value" to be mint in the wallet address. It simply adds the value to the balances variable using address and also adds the value to the totalSupply. The burn function is similar to mint. It simply burns the value i.e. subtracts the value from the balances variable using address and also subtracts the value from the totalSupply. 
The program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract token {

    // public variables here
    string public tokenName = "PHOENIX";
    string public tokenAbbrv = "PHX";
    uint public totalSupply = 0;


    // mapping variable here
    mapping(address => uint) public balances;
    
    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] > _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the burn, mint function after providing the address and value on the left side of the IDE. After clicking on transact you can mint/burn tokens.

## Authors

Rajendra Kumar Shaw
linkedIn:- https://www.linkedin.com/in/rajendra-kumar-shaw-824874203


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
