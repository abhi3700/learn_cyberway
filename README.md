# Cyberway Blockchain
- A fork of EOS Blockchain
- Uses EOSIO Software
- Flagship DApp: Golos (An incentivized social network)

## Technology
### System Contracts
* bios
`cyber.bios` smart contract is used as a link between operations in smart contract & the node core.
> Smart Contract <-----BIOS-----> Node core

	- `newaccount`: used to create a new account
```cpp
void newaccount(
	name creator,
	name name,
	authority owner,
	authoriry active
	)
```
		+ accessible to users
	- `setprods`: used when creating a block production schedule
```cpp
[[eosio::action]] void setprods(
	eosio::producer_key schedule
	)
```
> schedule - a list of validator keys
		+ not accessible to users, but system accounts
	- `setparams`: used to configure system params
```cpp
[[eosio::action]] void setparams(
	eosio::blockchain_params params
	)
```
> params - a structure containing settable system parameters
		+ not accessible to users, but system accounts
	- `reqauth`: used to verify user's signature
```cpp
[[eosio::action]] void reqauth(name from)
```
> from - user account
		+ accessible to users

	- `setabi`: upload ABI-description to an account
```cpp
[[eosio::action]] void setabi(
	name account,
	std::vector<char> abi
	)
```
> Parameters:
	- account - to which ABI description is uploaded
	- abi - an array of bytes containing ABI-description
		+ accessible to users

	- `setcode`: used to upload smart contract code to an account
```cpp
[[eosio::action]] void setcode(
	name account,
	uint8_t vmtype,
	uint8_t vmversion,
	std::vector<char> code
	)
```
> Parameters:
	- account - the name to which code is uploaded
	- vmtype - type of smart contract (virtual machine), or else set to <0>
	- vmversion - version of smart contract (virtual machine), or else set ot <0>
	- code - an array of bytes containing smart contract code
		+ accessible to users
	







#### Application Contracts
##### GOLOS
- Charge
- Control
