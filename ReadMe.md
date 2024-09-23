# ethproof
## Overview
MyToken is simple ethereum smart contract that represent a basic token with functionalities to mint and burn token .
## Requirement
1. PUBLIC VARIABLE--token_name,token_abbrv,total_supply(details about token)
2. MAPPING ADDRESS--map addresses to their respective balances 
3. mint FUNCTION--increase toltal_supply and balance 
4. burn FUNCTION--decrase the total_supply and balance and using if statemnet 
5. CONDITIONAL STATEMENT IN burn FUNCTION
   
## Contract details 

### public variable 
- string public token_name = "meta";
- string public token_abbrv = "MTA"; 
- uint public total_supply = 0;

  ### Mapping

- mapping (address => uint) public balances;

### Mint Function-
To mint tokens, call the mint function with the address to receive the tokens and the amount of tokens to mint.
solidity

function mint(address _address, uint _value) public {
    total_supply += _value;
    balances[_address] += _value;
}


### Burn funtion--
To burn tokens, call the burn function with the address from which to burn the tokens and the amount of tokens to burn. Ensure the address has enough balance to burn the specified amount.
solidity
function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        total_supply -= _value;
        balances[_address] -= _value;
    }
}
`
