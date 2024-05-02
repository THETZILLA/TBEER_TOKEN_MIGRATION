# TBEER_TOKEN_MIGRATION
TUTORIAL ON HOW TO DO THE TOKEN MIGRATION FOR TBEER

Wallet example:

![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/5abb4c91-e16b-4134-9cd2-7a1743ee94ff)

# 1) Add the new contract to your theta wallet:
- Token Contract Address:  0x444dc1ec5419ef6ca680592e871dc4c73c678582
- Symbol: TBEER
- Decimals: 18
![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/29bd3c35-dcc1-4ce8-8c76-c150fbacb662)

You should now be able to see the new token with the new logo in your wallet:
![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/e991d98f-7440-499f-a8f1-00b3000a7cf7)

# 2) Now, you need to approve the token migration by first allowing the new TBEER contract to access the funds from your account. The new TBEER contract ensures that ONLY TBEER tokens are swapped by hard-coding the old contract address (only tokens from that specific contract address can be swapped—NO OTHER TOKENS CAN BE SWAPPED).
![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/d82d93a1-4385-4c87-972d-efa2288d2cdc)


To do this, follow these steps:

Go to the contract tab in your wallet.
Paste the following information:
- Contract Address (Old TBEER CA): 0xc028a2be843cb1153b1531399d0e591100e35de7
- ABI/JSON Interface: (Copy the content from the “old_ABI” file added to this repository).
- Function: approve
- Spender (New TBEER Contract Address): 0x444dc1ec5419ef6ca680592e871dc4c73c678582
- Amount: Enter a very high number, as shown below—note that TBEER has 18 decimals, which is why there are so many digits: 9999999999999999999999999999999999999999999999999

![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/d72e4bf4-7145-4bfe-9da4-391e20418bf3)

Click on write, and enter your wallet password and confirm the transaction.

