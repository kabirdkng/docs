IDE Functionality
=================
Getting Started with the TokenGo IDE
-------------------------------------
The `TokenGo <http://tokengo.fun>`_ IDE is a powerful tool for creating and managing our own cryptocurrency tokens on Kadena Blockchain. Now we shall follow these steps to get started:

Prerequisites Before we start generating our token on testnet
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
* First, we download the eckoWallet extension from `chrome web store <https://chromewebstore.google.com/detail/eckowallet/bofddndhbegljegmpmnlbhcejofmjgbn>`_. Then we create our Kadena account.
.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest1.png
   :alt: chrome web store
   :align: center
* After creating our Wallet, we need to set the wallet network to 'testnet' in the top left corner and copy the account name starting with "k:" by clicking on it.
.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest2.png
   :alt: Ecko Wallet initial
   :align: center
* We need some test KDA to test our IDE, so we go to Kadena `faucet <https://tools.kadena.io/faucet/new>`_ , then we paste our account name in the public key field and delete "k:" from the account name and click on plus (+) Button, then we can see our account name and chain Id selected to chain 1. Now we press 'Create and fund account', and it will submit a transaction for us on the blockchain and give us a request key.
.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest3.png
   :alt: request test coin
   :align: center
* After confirmation, we returned to our eckoWallet extension and now see 20 KDA appear in our Wallet.
.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest4.png
   :alt: Ecko wallet with test coin
   :align: center


preparing Ecko wallet for testing
==================================
Now that we have testnet Kadena in our Wallet, let's visit the `tokenGo <http://tokengo.fun>`_ site and click on 'Connect Wallet', select 'Ecko wallet', then we sign with our Wallet, click save and boom, we are into it.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest5.png
   :alt: Ktg Wallet connect
   :align: center

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest6.png
   :alt: KTG Create Token Initial
   :align: center

Like me, if you are using a new wallet and following our prerequisites, we shall see a green button, "Initiate Cross-Chain Transaction", and all of the chain statuses will be red except chain one because we have testnet KDA on chain 1. As our Wallet is new and we don't have KDA on all the chains, clicking it will automate the transaction and transfer KDA to all of them. Now, let's click and sign it with our Wallet.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest7.png
   :alt: KTG sign xChain transaction
   :align: center

After signing the batch transactions, we can see their processing, and here, we need to wait for block confirmation. We can also close the window now.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest8.png
   :alt: processing transactions
   :align: center
 
After the transactions are processed, we can see all the chains are showing green, which means we are ready to generate our first token on Kadena Blockchain.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest9.png
   :alt: Ready to generate a token
   :align: center

Here, we can see that our Wallet now has a balance on all the chains, and Chain 1 still has 12.4 KDA, but we need at least 15 KDA or 150,000 HERON to test the token generator. For this walkthrough, we shall use KDA to generate our token.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest10.png
   :alt: Wallet after X-chain transfer
   :align: center

So, now again, we are heading towards Kadena's `faucet <https://tools.kadena.io/faucet/existing>`_ and requesting 20 test KDA on chain 1. This time, we don't need to delete the "k:" from our account name; we paste our account name and click on "Fund 20 Coins."

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest11.png
   :alt: faucet existing account
   :align: center


Generating our first token
===========================
Now we have enough KDA to generate our first simple fungible token, we need to give it a name; in our case, we are generating a sweet, simple test token, so we are giving our 

| Module(token) name "sweet-token" (you should give a unique module name here)
| Symbol "SWEETY", (this will be our token identifier for this walkthrough)
| Total supply 1 Billion (total supply of the generated token)
| Warrior Heron image link as the logo URL. (this should be a link of your token logo hosted online)


We can use KDA and HERON both here to generate our token, if we use KDA it will eventually convert to HERON and execute the transaction, and if we use HERON, we can get a 5% discount on the generation fees. Anyways, we just selecting KDA and clicking on "Generate Token - Cost: 15 KDA"

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest12.png
   :alt: token Details fillup
   :align: center

Now we can see the eckoWallet pop-up, and it shows all the commands to sign for the token generation; we scrolled to the bottom and clicked on "confirm" to submit the transaction. After submitting the transaction, we need to wait for block confirmation.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest13.png
   :alt: submit transaction
   :align: center

After the block confirmations, we shall see all the transactions completed and now our `TokenGo <http://tokengo.fun>`_ generated SWEETY token is deployed to the Kadena blockchain (testnet).

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest14.png
   :alt: Transactions Completed
   :align: center


viewing our generated token in the Ecko wallet
-------------------------------------------

To view our token in the ecko wallet, we need to add the contract address and SYMBOL of our token to eckoWallet by clicking on the plus (+) Button in our eckoWallet.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest25.png
   :alt: adding a token to Wallet
   :align: center

This shall open a form to put our token contract address and token Symbol; now we add them and click on Add Token Button. (If you are having issue finding your token address, your token address will be namespace.module-name in our case  n_f841e63968ab2acf9be57858cd1f64336e2a9310 our Namespace, and sweet-token our module name)

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest26.png
   :alt: token add form
   :align: center

After adding our token, we can see our token symbol along with other tokens in the Wallet, and now we can see that we have 1 billion SWEETY tokens in our Wallet.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest27.png
   :alt: Wallet with tokens
   :align: center


As we can see, the tokens are in our Wallet, and now it's time to manage our newly created token. 


Managing our token
===================
Now that our simple token is generated, we can set dex pair, get dex pair and also set Liquidity for the token to trade on the dex. lets get into them one by one.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest15.png
   :alt: ide initial
   :align: center

To manage our contract, first, we need to select our contact, for that, we shall click on "Manage Smart Contract" in the right-side settings panel, and then we can see some options to manage smart contracts. We should click on "Select contract".

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest16.png
   :alt: manage Smart contract
   :align: center

We can now see a modal to search for smart contracts; also, we can see our newly generated token contract highlighted in green, indicating that we are the owner of the smart contract. We shall now select our token by clicking on it.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest17.png
   :alt: select token contract
   :align: center

After selecting our token, we can now see our token address is showing under Manage Smart Contract. Now, we are ready to manage our smart contract.

Creating dex pair for our token
-------------------------------

First, we shall set a dex pair to trade on the dex, for that we are clicking on "Set Dex Pair" button.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest18.png
   :alt: set dex pair
   :align: center

by clicking on set dex pair, we can now see pact command to create a dex pair on the pact window,

``(n_3b878bdca18974c33dec88e791dd974107edc861.exchange.create-pair coin n_f841e63968ab2acf9be57858cd1f64336e2a9310.sweet-token "")``

where 

``n_3b878bdca18974c33dec88e791dd974107edc861.exchange.create-pair``
this is the pact command to create a pair on the dex

``coin``
this the the quote currency we wish to pair with in our case its (KDA)

``n_f841e63968ab2acf9be57858cd1f64336e2a9310.sweet-token``
and this is our sweet-token contract address.

Now, as we are keeping it simple for the first time, we now click on "Test sign" to see our code is working as intended, it will open our Wallet to test sign the command

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest19.png
   :alt: test sign
   :align: center

As we can see, it is working fine, next we shall click on the submit Button and confirm in our Wallet to submit the transaction to the blockchain.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest20.png
   :alt: Wallet confirm
   :align: center

After confirming with our Wallet it will submit the transaction and give us the requested key

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest21.png
   :alt: request key
   :align: center

Just a few moments and the transaction gets confirmed by the blockchain. Now, we successfully created dex pair for our newly created token.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest22.png
   :alt: transaction success
   :align: center

Next, we are going to check the dex pair data we just created.

Getting data of dex pair for our token
--------------------------------------

To get data of dex pairs for our token, we click on "Get Dex Pair Data"

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest23.png
   :alt: get dex pair data
   :align: center

After clicking in the pact window, we can see there is again a code 

``(n_3b878bdca18974c33dec88e791dd974107edc861.exchange.get-pair coin n_f841e63968ab2acf9be57858cd1f64336e2a9310.sweet-token)``

This code is a pact function to get pair details of the dex

Below the code, we also can see 

**TX Hash: x2KKfixvXYsxFkbN-OcY_UfkrmKbtSRmuvGQZTzlbfk**

Which is the generated transaction hash, also we can see 

**Tx Results**

.. code-block:: json 

 {
  "last-k": 0,
  "leg1": {
    "reserve": 0,
    "token": {
      "refSpec": [
        {
          "namespace": null,
          "name": "fungible-xchain-v1"
        },
        {
          "namespace": null,
          "name": "fungible-v2"
        }
      ],
      "refName": {
        "namespace": "n_f841e63968ab2acf9be57858cd1f64336e2a9310",
        "name": "sweet-token"
      }
    }
  },
  "fee-account": "fyhk3TyfP7NRMBBCNRi5ePKFV0x4zRzXE89T6STZeto",
  "locked": false,
  "guard": {
    "args": [],
    "fun": "n_3b878bdca18974c33dec88e791dd974107edc861.exchange.enforce-null"
  },
  "account": "VgmjEpmAL4hE2I6_QAsvpT3hMHKjXpkMPc79-KzdZsI",
  "fee-guard": {
    "args": [
      "coin:n_f841e63968ab2acf9be57858cd1f64336e2a9310.sweet-token"
    ],
    "fun": "n_3b878bdca18974c33dec88e791dd974107edc861.exchange.enforce-fee-access"
  },
  "leg0": {
    "reserve": 0,
    "token": {
      "refSpec": [
        {
          "namespace": null,
          "name": "fungible-xchain-v1"
        },
        {
          "namespace": null,
          "name": "fungible-v2"
        }
      ],
      "refName": {
        "namespace": null,
        "name": "coin"
      }
    }
  }
 }

This json is the data of dex-pair for KDA and our token, as we can see, the data contains the dex pair we just created, lets move forward to adding Liquidity to our pair so people can trade our token in the dex.

Adding Liquidity to our dex pair
--------------------------------
For the first time, we shall add the initial Liquidity of our token so that it can be traded in the dex with a ratio for our pair.

For that, first, we click on "Set Dex Liquidity" button, and it will open a modal to set the initial Liquidity for our dex pair

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest24.png
   :alt: Set initial liquidity modal
   :align: center

Now we shall add the KDA amount and our token amount to add Liquidity for our pair; we are giving 7 kda and 500K tokens for Liquidity (you can set Liquidity in whatever ratio you want).
Then, we will click on the Submit button.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest28.png
   :alt: liquidity form
   :align: center

After clicking on submit, we can now see the code in our pact window 

``(use n_3b878bdca18974c33dec88e791dd974107edc861.exchange)``
``(add-liquidity coin n_f841e63968ab2acf9be57858cd1f64336e2a9310.sweet-token (read-decimal 'kdaAmount) (read-decimal 'tokenAmount) 0.0 0.0 "k:1c6cbbb34a8ef4f745738a9a7eb324db84b21e1e015c55f2c83cb1a9917198e8" "k:1c6cbbb34a8ef4f745738a9a7eb324db84b21e1e015c55f2c83cb1a9917198e8" (read-keyset 'ks))``

This is the code to add Liquidity for our pair, now if we need to see the env data or make changes in the ratio, we can click to "Show Env Data" in the settings panel; it will show the env data in our pact window

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest29.png
   :alt: env data
   :align: center

Next, we are going to test sign the command to see if everything is working fine.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest30.png
   :alt: test sign
   :align: center

After signing the command with our eckoWallet, we can see

.. code-block:: json

 {
   "amount0": 7,
   "amount1": {
    "decimal": "500000.000000000000"
    },
  "supply": 1870.82869338697,
  "liquidity": 1870.72869338697 
 }

It seems our transaction is going to be successfull, now lets Submit the Transaction by clicking on the submit Button

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest31.png
   :alt: submit tx
   :align: center

After clicking submit our Wallet popped up and now we need to sign by clicking on confirm to submit the transaction to the blockchain

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest32.png
   :alt: Wallet confirm
   :align: center

Upon confirming, it will submit the transaction and generate a request key, after block confirmation we can see our transaction is successfull and we successfully added Liquidity in our dex pair.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest33.png
   :alt: trasaction successful
   :align: center


Swapping our newly generated token on the dex
===============================================

As now we have successfully added Liquidity to our SWEETY/KDA pair, we can now swap one to another in our Dex. to do that, first we need to click on "User Commands" tab inside our manage smart contract menu, then we can see a option named "Swap Tokens". we need to click there.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest34.png
   :alt: Swap token option
   :align: center

After clicking on swap token now a modal pops up infront of us to swap tokens, here we are giving 1.01 KDA and it is showing us that we shall receive estimated 62880 SWEETY tokens, now after checking it we hit the submit Button.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest35.png
   :alt: Swap form
   :align: center

After submitting the form we now can see PACT code to swap our tokens in the pact window.

``(n_3b878bdca18974c33dec88e791dd974107edc861.exchange.swap-exact-in``
        
``(read-decimal 'amountKDA)``
        
``(read-decimal 'amountTokenWithSlippage)``
        
``[coin n_f841e63968ab2acf9be57858cd1f64336e2a9310.sweet-token]``
        
 ``"k:1c6cbbb34a8ef4f745738a9a7eb324db84b21e1e015c55f2c83cb1a9917198e8"``
        
 ``"k:1c6cbbb34a8ef4f745738a9a7eb324db84b21e1e015c55f2c83cb1a9917198e8"``
        ``(read-keyset 'ks))``

now we need to test sign the transaction to see if everything is alright

after test sign we now can see our preflight transaction results

now as we can see our transaction, now we shall click on submit to Sign and send the transaction to the blockchain.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest36.png
   :alt: transaction results
   :align: center

Now, let's confirm the transaction.

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest37.png
   :alt: wallet confirmation
   :align: center

After confirming, it gave us a transaction hash, upon block confirmation it becomes green and we successfully swapped kda for our `TokenGo <http://tokengo.fun>`_ generated SWEETY token. 

.. image:: https://kai-docs.nyc3.cdn.digitaloceanspaces.com/ide/idetest38.png
   :alt: Transaction hash
   :align: center

Now, lets copy our transation hash check our transaction on `kadena block explorer <https://explorer.chainweb.com/>`_ dont forget to set the network to testnet. thats all for now, keep exploring and have fun with `tokengo.fun <http://tokengo.fun>`_
