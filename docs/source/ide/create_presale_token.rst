Creating a Presale Token with TokenGo IDE
=========================================

Hello friends! Today we are going to generate the required smart contracts for a token presale with zero code using `TokenGo IDE <https://tokengo.fun>`_.

Overview of Token Presale
-------------------------
A token presale is an early fundraising event where projects sell their tokens to early investors before the public sale. These tokens are offered at a discounted price with benefits for early supporters.

In TokenGo IDE, we can create a token presale smart contract without writing any code.

Prerequisites for Generating a Presale Token
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Like creating a regular token, we need KDA or HERON to generate a presale token. In TokenGo, we will need 15 KDA to generate our presale token. First, we head to the `Kadena Faucet <https://tools.kadena.io/faucet/new>`_ and request 20 KDA on Chain 1.


.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale1.png
   :alt: kda balance
   :align: center

Now that we have enough KDA to create our presale token, we can start generating it.

**Info:** If you are using our token generator for the first time, you will see a green button to initiate cross-chain transfer, and all chains except the one you have KDA on will be red. We discussed this in detail in our previous section on the token generator.

Creating the Presale Contract
=============================

In TokenGo, we are creating a token with the following details:

| **Module(token) name :** "sale-token" (you should give a unique module name here)
| **Symbol :** "SALE", (this will be our token identifier for this walkthrough)
| **Total supply :** 1 Billion (total supply of the generated token)
| **Image link :** URL for the token logo (this should be a link to your token logo hosted online)

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale2.png
   :alt: Module Details
   :align: center

After filling in the details for the token, click on "Show Advanced Options" and select "Pre-sales Contract". A form for inputting details of the token sale will appear. Here’s the breakdown of each option:

Filling Up the Presale Contract Form
------------------------------------
In TokenGo, we can set up our sales in two different phases: "phase-0" is the whitelisted sale, where whitelisted users can buy a limited amount of tokens at a discounted price, and "phase-1" is the public sale round, where any user with a wallet and KDA can buy any amount of available tokens.

**Total Batches for Sale :**
A batch is the unit of tokens in the presale. All calculations for phases 0 and 1 of the presale contract will be based on these batches. For our tutorial, we are going to sell a total of 100,000 batches, so we enter 100,000 here.

**Amount of Tokens Per Batch :**
This is the amount of tokens allocated per batch, the smallest unit for our presale. In this case, we set the amount per batch to 3000 tokens. Each batch will have 3000 tokens, so if any user buys a batch in the presale, they will receive 3000 SALE tokens.

**Pre-sales Amount (Auto-calculated) :**
This is the total amount of tokens that will be sold in the presale, auto-calculated by the system. In our case, it shows 300,000,000, which is 30% of our total supply, planned for sale during the presale period.

**Liquidity Account Amount :**
This is the amount of tokens allocated to the liquidity account. These tokens are not sold or held by the team but can be used to set liquidity pairs on a DEX after the presale ends. We are setting our liquidity token amount to 500,000,000, which is 50% of the total supply.

**Treasury Amount (Auto-calculated) :**
This is the amount of tokens allocated to the treasury, which can be used by the token creator for project development, marketing, or other purposes. This is auto-calculated by the system, and we see 200,000,000, meaning 20% of the total supply will be held by the treasury.

**Whitelist Reservations :**
This is the number of batches reserved for a whitelisted user in phase-0. We are setting our whitelist reservation to 100, so each whitelisted wallet can buy a maximum of 100 batches or (3000 x 100) = 300,000 tokens in phase 0.

**Phase 0 Whitelist Start Date and Time :**
This is the date and time for the phase-0 whitelist sale to start. We set it to 01/08/24 00:30 (it should be at least 12 hours after the token contract is generated).

**Phase 0 Price in KDA :**
 We set the price for 1 batch of tokens (3000 tokens in our case). We initially set the phase-0 whitelist sale price to 5 KDA per batch.

**Phase 1 Public Sale Start Date and Time :**
This is the date and time for the phase-1 public sale to start. We set it to 03/08/24 00:30.

**Phase 1 Price in KDA :**
We set the price for 1 batch of tokens (3000 tokens in our case). We set the phase-1 public sale price to 10 KDA per batch.

**End of Sales Date and Time :**
This is the date and time for the presale to end. We set it to 15/08/24 00:30. After this time, users cannot buy from the sales contract, and the token creator can distribute tokens and end the sale. after calling end sales unsold tokens will be transferred to the treasury.(we shall discuss it in later sections)

The supply chain is auto-selected as ecko, so we proceed with that.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale3.png
   :alt: Sales Details
   :align: center

After checking the details carefully, we submit our transaction to the blockchain by clicking "Generate Token - cost 15 KDA". This opens our wallet to sign the transaction.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale4.png
   :alt: Submit Tx
   :align: center

Click "Confirm," and the transaction for creating our presale token will begin processing.

In a few moments, the transaction is confirmed, and all transactions are green, indicating that we have successfully generated our presale token.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale5.png
   :alt: Confirmed Tx
   :align: center


Managing Our Newly Created Presale Token Contract
=================================================

To manage our newly created presale token, navigate to the IDE tab and click on "Select Contract" under the "Manage Smart Contract" menu in the right-hand side settings panel.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale6.png
   :alt: Select Contract
   :align: center

This opens a window to search for contracts, where we can see all deployed contracts, including our newly deployed contract, "sale-token." Select the sale token contract.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale7.png
   :alt: Select sale Contract
   :align: center

Updating the Prices(Before presale Starts)
------------------------------------------
If we want to update the price for a batch, we can do so before the phase-0 start time set during the creation of the presale token. Initially, we set 5 KDA and 10 KDA per batch for phase-0 and phase-1, respectively.

To update the price, click "Update Prices (before sale begins)."

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale8.png
   :alt: Update Prices
   :align: center

This opens a modal displaying the currently set prices for phase-0 and phase-1. In our case, it shows 5 KDA and 10 KDA per batch.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale9.png
   :alt: Current prices
   :align: center

We set our new batch price to 6 KDA per batch for phase-0 and 9 KDA per batch for phase-1 and click submit.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale10.png
   :alt: Submit new Prices
   :align: center

After clicking, it shows the code to update the price in the IDE Pact viewer. We then submit and sign our transaction.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale11.png
   :alt: Submit new Prices
   :align: center

Our wallet prompts us to sign the transaction. Click "Confirm" in the eckoWallet.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale12.png
   :alt: Sign Transaction
   :align: center

After signing, we receive a transaction hash, and the transaction will eventually be confirmed by the blockchain if our data is valid.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale13.png
   :alt: Sign Transaction
   :align: center

Now, the new batch prices for phase-0 and phase-1 are successfully set. We just need to wait for the whitelist sale (phase-0) to start.

Whitelist Sales
----------------
A whitelist sale is a special type of presale where only whitelisted users can participate. For our sale-token, a whitelisted user can buy up to 100 batches of SALE tokens. To whitelist accounts, we need to call the whitelist user function, which will reserve 100 batches for each whitelisted wallet address.

Whitelist wallet Addresses
~~~~~~~~~~~~~~~~~~~~~~~~~~
As phase-0 has started, it's time to whitelist wallet addresses. To do this, we need to call the "Whitelist Sales" function under the "Manage Smart Contract" section on the left-hand side settings panel.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale14.png
   :alt: WhiteList Sales
   :align: center

Clicking on it will open a modal to input wallet addresses. Let's fill in some wallet addresses for whitelist sales.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale15.png
   :alt: WhiteList wallet
   :align: center

After adding a wallet address, click on "Add Whitelist" to add the wallet address to the whitelist. This will show a new input field for wallet address input.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale16.png
   :alt: WhiteList addresses
   :align: center

After adding all the whitelist addresses, click on submit.

Submitting the form adds code to the IDE pact window, which will whitelist the wallet addresses for phase-0 sales. In our case, it will reserve 100 batches for each wallet address.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale17.png
   :alt: WhiteList Code
   :align: center

Now that we have added all the whitelist addresses, submit and sign the transaction. Click on submit in the settings panel, which prompts your wallet to sign the transaction.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale18.png
   :alt: WhiteList Submit
   :align: center

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale19.png
   :alt: WhiteList Sign
   :align: center

After signing the transaction with your wallet, it submits the transaction to the blockchain and shows a transaction ID, which is eventually confirmed.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale20.png
   :alt: Txn Hash
   :align: center

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale21.png
   :alt: Confirmed Tx
   :align: center


Buying Whitelisted tokens
-------------------------
After transaction confirmation our whitelisted users can buy from the phase-0 presale using their wallet.

After transaction confirmation, our whitelisted users can buy from the phase-0 presale using their wallet. We will now connect a wallet that is already whitelisted. For this, we will use Wallet Connect in Linx Wallet (or any WalletConnect compatible wallets like X-wallet, Zelcore, Koala, etc.).

Connecting wallet using linx wallet wallet connect
--------------------------------------------------
First, click on "Connect Wallet" and select WalletConnect. It will open a QR code in front of us.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale22.png
   :alt: Connect Wallet
   :align: center

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale23.png
   :alt: Wallet Connect
   :align: center

Open the Linx Wallet app on your mobile.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale27.png
   :alt: Linx Wallet Mobile
   :align: center

After opening the Linx Wallet app, click on "Scan" to open the camera and scan the QR code.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale24.png
   :alt: Scan option
   :align: center

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale25.png
   :alt: Scan Qr code
   :align: center

After scanning the QR code, your wallet prompts you to accept the connection request. Click on "Accept," and you are now connected to TokenGo with your Linx Wallet using WalletConnect.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale26.png
   :alt: Accept Connection request
   :align: center

Buying Using Wallect Connect (Linx)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Now that our wallet is connected to the site, we can buy tokens. First, select the contract as we did before.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale28.png
   :alt: select Contract
   :align: center

It opens a window to search for modules. Search for our module name "sale-token" and select it.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale29.png
   :alt: search contract
   :align: center

Now, click on "User Commands."

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale30.png
   :alt: User Commands
   :align: center

Click on "Buy" to open a form to input the batch count you want to buy.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale31.png
   :alt: Buy Command
   :align: center

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale32.png
   :alt: Buy submit
   :align: center

The form shows that you have a reserved batch, and the price for a batch is 6 KDA. Let's submit it.

After submitting, the IDE displays the code. Since we want to buy only one batch, we just submit the transaction.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale33.png
   :alt: Buy submit tx
   :align: center

After submitting, a transaction to sign in our Linx Wallet pops up, showing the expected transaction result as success. Tap on "Approve."

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale34.png
   :alt: Linx Tx Approve
   :align: center

Upon approving, the TokenGo app shows a transaction hash, and it eventually gets blockchain confirmation.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/presale36.png
   :alt: Confirmed Tx
   :align: center

We have now successfully bought our whitelisted presale token. We bought 1 batch out of our reserved 100 batches, and we can buy 99 more batches during the presale period.