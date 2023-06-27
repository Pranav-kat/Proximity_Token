# Proximity Token - PRX Contract

This Solidity program is a simple smart contract that demonstrates the functionality of the Solidity programming language. The purpose of this program is to create addresses and to mint and burn as many PRX tokens as the user wishes to.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has two functions mint() and burn() that creates and destroys the PRX tokens .

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., CreateToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
   string public tokenName = "PROXIMITY";
   string public tokenAbbrv = "PRX";
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
      if (balances[_address] >= _value){
      totalSupply -= _value;
      balances[_address] -= _value;
      }
   }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile CreateToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "CreateToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by firstly adding the address and the token value to be minted. Click on the "CreateToken" contract in the left-hand sidebar, and then click on the "mint" function. Finally, click on the "transact" button to execute the function and retrieve the total supply of tokens.

## Authors

Pranav Katte
