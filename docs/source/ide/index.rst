IDE Functionality
=================
Getting Started with the TokenGo IDE
-------------------------------------
The `TokenGo <http://tokengo.fun>`_ IDE is a powerful tool for creating and managing your own cryptocurrency tokens on Kadena Blockchain. Follow these steps to get started:

Prerequisites Before we start generating our token on testnet
-------------------------------------------------------------
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


let's start testing
====================
Now as we have testnet Kadena in out wallet, let's visit the `tokenGo <http://tokengo.fun>`_ site and click on 'Connect Wallet', select 'Ecko wallet' then we sign with our wallet, click save and boom we are into it.

.. image:: path/to/idetest5.png
   :alt: Ktg wallet connect
   :align: center

.. image:: path/to/idetest6.png
   :alt: KTG Create Token Initial
   :align: center

like me, if you are using a new wallet and followed our prerequisites we shall see a green button "Initiate Cross-Chain Transaction" and all of the chain status will be red except chain 1, as we have test KDA on chain 1. As our wallet is new and we dont have KDA on all the chains, clicking it will automate the transation and will transfer KDA to all now lets click it and sign it with our wallet.

.. image:: path/to/idetest7.png
   :alt: KTG sign xChain transaction
   :align: center

after signing the batch transactions we can see its processing, and here we need to wait for block confirmation, we also can close the window now.

.. image:: path/to/idetest8.png
   :alt: KTG sign xChain transaction
   :align: center
 

