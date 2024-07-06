IDE Functionality
=================
Getting Started with the TokenGo IDE
-------------------------------------
The `TokenGo <http://tokengo.fun>`_ IDE is a powerful tool for creating and managing your own cryptocurrency tokens on Kadena Blockchain. Follow these steps to get started:

Prerequisites Before we start generating our token on testnet
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
* First we download the eckoWallet extension from `chrome web store <https://chromewebstore.google.com/detail/eckowallet/bofddndhbegljegmpmnlbhcejofmjgbn>`_. then we create our kadena account.
.. image:: path/to/idetest1.png
   :alt: chrome web store
   :align: center
* After creating our wallet, we need to set the wallet network to 'testnet' on the top left corner and copy the account name starting with "k:" by clicking on it.
.. image:: path/to/idetest2.png
   :alt: Ecko wallet initial
   :align: center
* we must need some test KDA to test our IDE, so we go to Kadena `faucet <https://tools.kadena.io/faucet/new>`_ , then we paste our account name in public key feild and delete "k:" from the account name and click on plus (+) button, then we can see our account name and chain Id selected to chain 1. Now we press 'Create and fund account', it will submit a transaction for us on the blockchain and give a request key.
.. image:: path/to/idetest3.png
   :alt: request test coin
   :align: center
* After confirmation we return to our eckoWallet extension and now we can see 20 KDA appeared into our Wallet.
.. image:: path/to/idetest4.png
   :alt: Ecko wallet with test coin
   :align: center


prepareing ecko wallet for testing
==================================
Now as we have testnet Kadena in out wallet, let's visit the `tokenGo <http://tokengo.fun>`_ site and click on 'Connect Wallet', select 'Ecko wallet' then we sign with our wallet, click save and boom we are into it.

.. image:: path/to/idetest5.png
   :alt: Ktg wallet connect
   :align: center

.. image:: path/to/idetest6.png
   :alt: KTG Create Token Initial
   :align: center

like me, if you are using a new wallet and followed our prerequisites, we shall see a green button "Initiate Cross-Chain Transaction" and all of the chain status will be red except chain 1, because we have test KDA on chain 1. As our wallet is new and we dont have KDA on all the chains, clicking it will automate the transation and will transfer KDA to all of them, now lets click and sign it with our wallet.

.. image:: path/to/idetest7.png
   :alt: KTG sign xChain transaction
   :align: center

after signing the batch transactions we can see its processing, and here we need to wait for block confirmation, we also can close the window now.

.. image:: path/to/idetest8.png
   :alt: processing transactions
   :align: center
 
after the transactions are processed, we now can see all the chains are showing green, this means we are now ready to generate our first token on Kadena Blockchain.

.. image:: path/to/idetest9.png
   :alt: Ready to generate token
   :align: center

here we can see now our wallet have balance on all the chains, and Chain 1 still have 12.4 KDA, but we need atleast 15 KDA or 150,000 HERON to test the Token generator. For this walkthrough we shall use KDA to generate our token.

.. image:: path/to/idetest10.png
   :alt: wallet after X-chain transfer
   :align: center

So, now again we are heading towards Kadena `faucet <https://tools.kadena.io/faucet/existing>`_ and requesting 20 test KDA on chain 1. this time we dont need to delete the "k:" from our account name, we just paste our account name and clicking on "Fund 20 Coins"

.. image:: path/to/idetest11.png
   :alt: faucet existing account
   :align: center


Generating our first token
===========================
Now we have enough KDA to generate our first simple fungible token, we need to give it a name, in our case we are generating a sweet simple test token, so we are giving our 

| Module(token) name "sweet-token" (you should give a unique module name here)
| Symbol "SWEETY", (this will be our token identifier for this walkthrough)
| Total supply 1 Billion (total supply of the generated token)
| Warrior Heron image link as the logo url. (this should be a link of your token logo hosted online)


We can use KDA and HERON both here to generate our token, if we use KDA it will eventually convert to HERON and execute the transaction, and if we use HERON we can get a 5% discount on the generation fees. Anyways, we just selecting KDA and clicking on "Generate Token - Cost: 15 KDA"

.. image:: path/to/idetest12.png
   :alt: token Details fillup
   :align: center

Now we can see the eckoWallet is popped up, and its showing all the commands to sign for the token generation, we scrolled to the bottom and clickd on "confirm" to submit the transaction. after submitting the transaction we need to wait for block confirmation.

.. image:: path/to/idetest13.png
   :alt: submit Transaction
   :align: center

after the block confirmations we shall see all the transactions completed and now our `TokenGo <http://tokengo.fun>`_ generated SWEETY token is deployed to Kadena blockchain (testnet).

.. image:: path/to/idetest14.png
   :alt: Transactions Completed
   :align: center

now we can see here "After Deployment, Manage your Contract from the IDE Tab" so now its time to manage our newly created token.

Managing our token
===================
Now as our simple token is generated, we now can set dex pair, get dex pair and also can set Liquidity for the token to trade on the dex. lets get into them one by one.

.. image:: path/to/idetest15.png
   :alt: ide initial
   :align: center

to manage our contract first we need to select our contact, for that we shall click on "Manage Smart Contract" in the right side settings panel, then we can see some options to manage smart contracts. We should click on "Select contract".

.. image:: path/to/idetest16.png
   :alt: manage Smart contract
   :align: center

we now can see a modal to search for smart contracts, also we can see our newly generated token contract address highlighted with green colour and its indicating that we are the owner of the smart contract. we shall select our token by clicking on it.

.. image:: path/to/idetest17.png
   :alt: select token contract
   :align: center

after selecting our token address we now can see our token address is showing under Manage Smart Contract, now we are ready to start managing our smart contract.



