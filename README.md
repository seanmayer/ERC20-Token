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

ICO Smart Contract

- ICO smart contract will accept ETH in exchange for the ERC20 Test (TST) token found here: https://github.com/seanmayer/ERC20-Token
- The TST token is a fully compliant ERC20 token
- TST will be generated at ICO time
- Investors will send ETH to the ICO contract's address, in return they get an amount of TST tokens

- TST token price in wei is: 1TST = 0.001ETH = 10**15 wei, 1ETH = 1000 TST
- The minimum investment is 0.01ETH and maximum investment 5ETH
- The ICO Hardcap is 300ETH
- ICO will have an admin, that specifies when ICO starts and ends
- TST token will be tradable only after a specific time set by the admin

- For an emergency the admin can stop the ICO 
- Can also change the deposit address in case it comprimised
- Also adding the ability to burn the tokens that were not sold in ICO
- After investment is made into the ICO the event will be emitted

Locking up Tokens

- Token lock up is being done for a period of time after the ICO ends
- This reduces the likelyhood of a price crash if investors descide to sell straight away at the same time
- The tokens should not be transferable straight away

Burning Tokens

- Burn can be called by anyone to initiate
- The token burn can be done after ICO completes
- Burning tokens can be used for a deflationary use, therefore this creates a higher value token