## MyToken Contract

This is a Solidity smart contract that implements a basic token called "MyToken". The contract allows users to mint (create) and burn (destroy) tokens.

## Public Variables
The contract has the following public variables:

'tokenName': A string representing the name of the token. In this case, the token name is "dotcoins".
'tokenAbbrv': A string representing the abbreviation of the token. In this case, the abbreviation is "marvel".
'totalSupply': An unsigned integer representing the total supply of the token. The initial value is set to 0.

## Mapping Variable
The contract uses a mapping called 'balances' to keep track of the token balances of different addresses. The mapping associates addresses with their respective token balances.

## Mint Function
The 'mint' function allows the creation of new tokens. It takes two parameters: '_address' (the address to mint tokens to) and '_value' (the amount of tokens to mint). The function increases the total supply by the '_value' and adds the minted tokens to the balance of the specified '_address'.

## Burn Function
The burn function allows the destruction of tokens. It takes two parameters: '_address' (the address to burn tokens from) and '_value' (the amount of tokens to burn). The function checks if the '_address' has a balance greater than or equal to the '_value' before reducing the total supply and deducting the burned tokens from the balance of the specified '_address'.

Please note that this contract lacks some important functionalities typically found in production-ready token contracts, such as transfer, approval, and event emission mechanisms. It serves as a basic example to demonstrate the minting and burning of tokens.

Note: Ensure that the Solidity version used for compiling the contract is at least 0.8.18.

### Executing program

```
pragma solidity 0.8.18;

  contract MyToken {

  // public variables here
  string public tokenName = "pingcoin";
  string public tokenAbbrv = "bread";
  uint public totalSupply = 0;

  // mapping variable here
  mapping (address => uint) public balances;
  // mint function
  function mint (address _address, uint _value) public {
      totalSupply += _value;
      balances [_address] += _value;    
  }
  // burn function
  function burn (address _address, uint _value) public {
      if (balances[_address] >= _value){
      totalSupply -= _value;
      balances [_address] -= _value;  
          }   
      }
  }

```
## Usage

To use this contract, follow these steps:

Deploy the contract to a compatible Ethereum development environment. Interact with the contract using an Ethereum wallet or a custom application. Call the mint function to create new tokens and increase the total supply. Call the burn function to destroy existing tokens and decrease the total supply, ensuring the balance of the "sender" is sufficient before performing the burn. Always exercise caution while using smart contracts on the Ethereum network and make sure to thoroughly test and verify the contract's functionality before deploying it in a production environment.
