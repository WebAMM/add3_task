# add3_task
goal 1:
ERC20 Token

I deploy the token on polygon testnet and also verify the code.
ERC20 token is fully secure, reliable, and efficient and consume less gas fee.

 Smart contract named MyToken that extends the functionalities of the ERC20, ERC20Burnable, Pausable, and Ownable contracts. This contract represents ERC-20 token with additional features for burning tokens, pausing/unpausing transfers, and being owned by a designated account.
Here's an overview of how the contract works and its main functionalities:

1.	Contract Inheritance:	
MyToken inherits from ERC20, ERC20Burnable, Pausable, and Ownable contracts.
2.	Constructor:
The constructor of the MyToken contract sets the token name as "MyToken" and the token symbol as "MTK" using the ERC20 constructor.
3.	Pausable Functionality:
The Pausable contract provides the ability to pause and unpause transfers of the token.
The contract owner (account that deploys the contract) can call the pause() function to pause transfers, preventing any further token transfers.
Similarly, the owner can call the unpause() function to resume transfers after they have been paused.
4.	Minting Tokens:
The mint() function allows the contract owner to mint new tokens and assign them to a specified recipient.
Only the owner can call this function. The owner can create new tokens and distribute them as needed.
5.	Burning Tokens:
The ERC20Burnable contract provides the ability to burn (destroy) tokens.
The contract owner can call the burn() function to burn a certain amount of their own tokens.
The burnFrom() function can be used by token holders who have allowed the contract to spend their tokens. It allows them to burn tokens within the limits of their allowance.
6.	Custom Token Transfer Hook:
The _beforeTokenTransfer() function is overridden from the ERC20 contract.
This function is called before every token transfer and ensures that transfers are only allowed when the contract is not paused (whenNotPaused modifier).
This custom hook enforces the pause functionality for all transfers.
7.	Ownership Management:
The Ownable contract provides basic access control, where the contract has an owner account that can manage certain functions.

The constructor assigns the contract deployer (creator) as the initial owner.
The owner can transfer ownership to another account using the transferOwnership() function. Ownership gives control over certain functions, like minting and pausing.
Overall, the MyToken contract is a modified ERC-20 token with additional features like pausing, burning, and minting, which provide flexibility and control to the token owner. 



Token address is: 
0x2703843549C9BE2eAcF3d4113EDa8CA91e48139D
I deployed it on polygone testnet : 
Link is : https://mumbai.polygonscan.com/address/0x2703843549c9be2eacf3d4113eda8ca91e48139d 



I also share you source code of this token.


Goal 2: 
Staking Contract:

Smart contract for a staking platform built on the Polygone TestChain. The contract allows users to deposit a specific token, stake it for a certain period of time, and earn rewards based on the staking duration. Let's break down the main components and how the contract works:
Interfaces and Libraries:

The ITRC20 interface represents the ERC-20 token standard functions that the staking contract interacts with.
The SafeMath library provides safe arithmetic operations to prevent overflows and underflows.
Contract Inheritance:

The Ownable contract serves as a base contract to manage ownership of the staking contract.
The Staking contract inherits from Ownable, indicating that it has owner-specific functions and modifiers.
Constructor:

The constructor initializes the staking contract with the address of the staking token (of type ITRC20).
It also initializes a mapping named allocation that associates staking durations (in days) with reward allocation percentages.

Struct and Mapping Definitions:

The userInfo struct holds various information about a user's staking activity.
The contract uses several mappings to keep track of user data, including deposited amounts, lockable days, deposit times, and more.
Events:

The Deposite_ event is emitted when a user makes a deposit.
Staking and Reward Mechanism

Users can stake a specified amount of tokens for a given number of lockable days using the farm function.
The contract calculates and accumulates rewards based on the allocation percentage and lockable days, updating user data accordingly.
The pendindRewards function calculates the rewards that are ready to be claimed by a user.
The harvest function allows users to claim their rewards. Rewards are either calculated based on the predefined allocation percentage or, if the lock-up period hasn't ended, they're calculated pro-rata.
Deduction percentages are applied to the staked amount in case users withdraw before the lock-up period ends.
Owner Functions:

The owner can change the deduction percentage and the time calculation unit.
The owner can withdraw excess tokens from the contract using emergencyWithdraw.
The owner can also withdraw excess BNB (if any) from the contract using emergencyWithdrawBNB.

User Information Queries:

The UserInformation function allows users to query their staking data, including deposited amounts, lockable days, and deposit times.
Modifiers:

The onlyOwner modifier restricts certain functions to be callable only by the owner of the contract.

Overall, this smart contract allows users to stake a specific token for various lockable periods and earn rewards based on the staking duration. It implements reward calculations, deduction percentages, and the ability for users to claim their rewards. The contract also provides emergency withdrawal functionality for the owner to manage the contract's assets.


Contract address: https://mumbai.polygonscan.com/address/0xeb210f2f39beb8e2c85326db9167a33b271b29c2 


