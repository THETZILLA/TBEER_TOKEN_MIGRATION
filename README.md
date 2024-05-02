# TBEER TOKEN MIGRATION
TUTORIAL ON HOW TO DO THE TOKEN MIGRATION FOR TBEER - MAY 2024.

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
- ABI/JSON Interface: (Copy the content from the “old_ABI” file added to this repository) - open on a new tab and then click on copy raw file:
  ![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/efa21202-31c3-4225-a4ba-18012bc82303)
- Function: approve
- Spender (New TBEER Contract Address): 0x444dc1ec5419ef6ca680592e871dc4c73c678582
- Amount: Enter a very high number - TBEER has 18 decimals, which is why there are so many digits (copy this): 9999999999999999999999999999999999999999999999999

![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/d72e4bf4-7145-4bfe-9da4-391e20418bf3)

Click on write, and enter your wallet password and confirm the transaction.


# 3) Now you are ready to interact with the new contract. Choose the appropriate function based on the type of amount you are migrating:
For whole amounts (e.g., 5 TBEER), use the function “migrateTokens_Whole.”
For decimal amounts (e.g., 2.5 TBEER), use “migrateTokens_Decimals.”

# 3.a) Migrate tokens whole:
- Paste the new Contract address: 0x444dc1ec5419ef6ca680592e871dc4c73c678582
- Paste the new ABI: (Copy the content from the “new_ABI” file added to this repository) - open on a new tab and then click on copy raw file:
  ![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/64712072-3830-4868-94b2-a6ae39fe6cec)
- Select the function: migrateTokens_Whole.
- Enter the amount: In this example, we will swap 5 TBEER.
![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/cdb8e59c-8a76-4cfe-9cc4-cd5ec79be364)

Here, we can observe how the new TBEER contract facilitates the token migration process. The contract is designed to swap the old TBEER tokens for new ones in the users' wallets. Additionally, it manages the swapping of tokens in the new TBEER development wallet. Below, you can find the balances before and after the token swap to verify the successful migration:

<img width="486" alt="image" src="https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/5db34b83-8a99-4e19-8ca7-bbfe6ccb7d5d">
This information demonstrates the contract's effectiveness in handling both user and developer token transactions during the migration phase.


# 3.b) Migrate tokens with decimals (This option is more complex due to how the Theta wallet handles decimals—please see the explanation below):

- Paste the new Contract address: 0x444dc1ec5419ef6ca680592e871dc4c73c678582
- Paste the new ABI again: (copy the content from the “new_ABI” file added to this repository).
- Select “migrateTokens_Whole”
- Enter the amount: In this example, we are going to swap 1.5 TBEER.

  ![image](https://github.com/THETZILLA/TBEER_TOKEN_MIGRATION/assets/156357319/cdf5ebb7-db15-4339-b523-c248b01b5844)

  Calculation of the decimals:

a) Count the decimal places the number has (number of digits after the decimal point) and subtract that from 18 (the number of decimals TBEER has).
b) Remove the decimal point from the number (1.5 becomes 15).
c) Add 17 zeros: 00000000000000000 (18 zeros minus 1 for the decimal point).
d) Merge them together to form: 15 followed by 17 zeros (15000000000000000000).

Copy the amount of zeros from here:

- 18 zeros: 000000000000000000
- 17 zeros: 00000000000000000
- 16 zeros: 0000000000000000
- 15 zeros: 000000000000000
- 14 zeros: 00000000000000
- 13 zeros: 0000000000000
- 12 zeros: 000000000000
- 11 zeros: 00000000000
- 10 zeros: 0000000000
- 09 zeros: 000000000
- 08 zeros: 00000000
- 07 zeros: 0000000
- 06 zeros: 000000
- 05 zeros: 00000
- 04 zeros: 0000
- 03 zeros: 000
- 02 zeros: 00
- 01 zero: 0
