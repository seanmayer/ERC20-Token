ERC Token Standard

- Token that is designed to represent something of value
- Characteristics such as voting rights or discount vouchers
- It can represent any fungible trading good
- ERC stands for "Ethererum  Request for Comments".
- ERC is a form of proposal and its purpose is to define standards and practices
- EIP stands for "Ethererum Improvement Proposal" 
- EIP makes changes to the actual code of Ethereum
- ERC20 is a Proposal, this standardise how a token contract should be defined, in the case of interacting with a token contract and how these contracts interact
- ERC20 is a standard interface, used by applications such as wallets, decentralised exchanges etc. to intract with tokens.

ERC Tokens Functions

- transfer() function is used to send tokens from one user to another, but this does not work well when tokens are being used to pay for a function in a smart contracts
- ERC20 standard defines a mapping data structure named allowed and 2 functions approve() and transferFrom() that permit a token owner to give another address approval to transfer to a number of tokens known as allowance
- Allowance for an address can only be set by the owner of that address

Understanding allowed, transferFrom() and approve()

- 2 step process, first the owner approves, the other account will transferFrom, so that it can transfer from it own account the approved number of tokens
- This is similar to a credit mechanism for credit limits are credit cards

- Imagine there are 2 users A and B. A has 1000 tokens and wants to give permission to B to spend 100 of them.

1. A will call: approve(address_of_B,100)
2. After that the allowed data structure will contain: allowed[address_of_A][address_of_B] = 100
3. If B wants later to transfer 20 tokens from A to its account, B will execute transferFrom(address_of_A, address_of_B,20)

- After calling the transferFrom() function (byB) the balance of A decreases by 20 and the balance of B increases by 20, which in turn the allowed mapping will contains: allowed[address_of_A][address_of_B] = 80