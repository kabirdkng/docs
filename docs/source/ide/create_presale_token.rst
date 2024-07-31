Creating a presale Token with Tokengo IDE
=========================================

Hello friends, today we are going to generate reqired smart contracts for a token presale with zero code in `TokenGo IDE <https://tokengo.fun>`_.

Overview of token presale
-------------------------
A token presale is a early fundrising event where projects sells their tokens to early investors before it goes live for public sale. Where the tokens are offered at a discounted price with benefits for early supporters.

In Tokengo IDE, we can create a token presale smart contract with zero code.

prerequisite for generating presale token
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
like creating a normal token we also need KDA or heron to genererate a presale token, here in Tokengo we shall need 15 KDA to generate our presale token. For that, first we head towards `Kadena Faucet <https://tools.kadena.io/faucet/new>`_ and request 20 KDA on Chain 1.


.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale1.png
   :alt: kda balance
   :align: center

Now as we can see we have enough KDA to create our presale token, we can start generating our token,

Info: If you are using our token generator for the first time, you shall see a green button to initiate cross chain transfer and all the chain except the chain you have KDA will be red in colour. we have discussed it in details on our previous section on token generator.

Creating the presale contract
=============================

In TokenGo we are creating a token with following details

| Module(token) name "sale-token" (you should give a unique module name here)
| Symbol "SALE", (this will be our token identifier for this walkthrough)
| Total supply 1 Billion (total supply of the generated token)
| image link as the logo url. (this should be a link of your token logo hosted online)

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale2.png
   :alt: Module Details
   :align: center

after filling up the details for the token we click on "Show Advanced Options", then select "Pre-sales Contract". now we shall see a form to input details of the token sales. here is the breakdown of each options.

Filling up presale contract form
--------------------------------
in tokenGo we can set up our sales in 2 different phases, "phase-0" is whitelisted sale, where every whitelisted users can buy a limited amout of token in a discounted price. and "phase-1" is public sale round where any user with a wallet and KDA can buy any amount of available tokens. 
**Total Batches for Sale :**
A batch is the unit of tokens in the presale, all the calculations for the phase-0 and phase-1 of the presales contract will be bound to this batches. for our tutorial we are going to sell a total of 100,000 batches in our presale, So we are giving 100,000 here.

**Amount of Tokens Per Batch :**
This is amount of tokens that will be allocated per batch, this amount is like the smallest unit for our presale, in this case we are setting our Amount per batch to 3000 tokens. So now each batch will have 3000 tokens, if any user buy a batch in the presale they will get 3000 SALE tokens.

**Pre-sales Amount (Auto-calculated) :**
This is the total amount of tokens that will be sold in the presale, this is auto-calculated by the system and will show us the value, in our case its showing 300,000,000 means 30% of our total supply, which we are planning to sale in the whole presale period.

**Liquidity Account Amount :**
This is the amount of tokens that will be allocated to the liquidity account, and it is the extra tokens that will not be sold or be held by the team, rather this amount can be used to set liquidity pair on DEX after the presale ends. we are setting our liquidity token amount 500,000,000 which is 50% of the total supply.

**Treasury Amount (Auto-calculated) :**
This is the amount of tokens that will be allocated to the treasury, which can be used by the token creator for project developement, marketing or whatever they wants, this is auto-calculated by system and now we can see here 200,000,000 that means 20% of the total supply will be help by the treasury.

**Whitelist Reservations :**
This is the number of batches that will be reserved for a whitelisted user in phase-0, we are setting our whitelist reservation to 100, so every whitelisted wallets can buy max 100 batches or (3000 X 100) = 300,000 tokens in phase 0.

**Phase 0 Whitelist Start Date and Time :**
This is the date and time for the phase-0 whitelist sale to start, we are setting it 01/08/24 00:30 (it should be minimum 12 hours after the token contract is generated)

**Phase 0 Price in KDA :**
we need to set the price for 1 Batch of tokens or in our case 3000 tokens. now we are setting the price for phase-0 whitelist sale to 5 KDA per Batch.

**Phase 1 Public Sale Start Date and Time :**
This is the date and time for the phase-1 public sale to start, we are setting it 03/08/24 00:30

**Phase 1 Price in KDA :**
we need to set the price for 1 Batch of tokens or in our case 3000 tokens. now we are setting the price for phase-0 whitelist sale to 10 KDA per Batch.

**End of Sales Date and Time :**
This is the date and time for the presale to end, we are setting it 15/08/24 00:30. after this time users cannot buy from the sales contract, and token creator can distribute tokens and can end the sales.

also we can set the supply chain here we can see ecko is auto selected, so we are going with this.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale3.png
   :alt: Sales Details
   :align: center

now as we checked the details carefully, now its time to submit our transaction to the blockchain. for this we click on "Generate Token - cost 15KDA" and it will now open our wallet to sign the transaction.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale4.png
   :alt: Submit Tx
   :align: center

now we need to click on Confirm, and it will show all the transactions for creating our presale token is now processing.

in a few moments the transction is confirmed, and now we can see all transaction are green that means we have generated our presale token successfully

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale5.png
   :alt: Confirmed Tx
   :align: center
