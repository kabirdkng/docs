Heron Token Contract
====================

The Heron token contract is designed as a community-driven utility themed memecoin with specific governance and tokenomics features. It enforces mass conservation and validates account names for transactions.

**Namespace**: ``n_e309f0fa7cf3a13f93a8da5325cdad32790d2070``

**Keyset Governance**: The contract uses a defined keyset for governance operations, ensuring that only authorized parties can perform certain actions.

Governance
----------

The governance of the Heron token is managed through the ``GOV`` capability, which is enforced by a predefined keyset. This ensures that administrative functions such as token initialization and premine allocation are securely controlled.

.. code-block:: lisp

    (defcap GOV ()
      (enforce-keyset "n_e309f0fa7cf3a13f93a8da5325cdad32790d2070.heron-token-gov"))

Tokenomics
----------

The tokenomics of the Heron token are initialized through the ``init-token`` function, which sets up the initial distribution of tokens based on predefined percentages for different accounts.

.. code-block:: lisp

    (defun init-token:[string] (init-data:object)
      @doc "Initialize the tokens for the contract"
    )

Capabilities
------------

The Heron token contract defines several capabilities for managing tokens, including ``DEBIT``, ``CREDIT``, ``ROTATE``, and cross-chain transfers. These capabilities enforce the rules around token transfers, account guard rotation, and inter-chain movements.

**DEBIT** and **CREDIT** Capabilities:

.. code-block:: lisp

    (defcap DEBIT (sender:string))
    (defcap CREDIT (receiver:string))

**ROTATE** Capability for Guard Rotation:

.. code-block:: lisp

    (defcap ROTATE (account:string))

**Cross-Chain Transfer** Capabilities:

.. code-block:: lisp

    (defcap TRANSFER_XCHAIN:bool (sender:string receiver:string amount:decimal target-chain:string))

Utility Functions
-----------------

The contract includes utility functions for account validation, balance queries, and administrative tasks like moving the premine and exempting accounts from transaction fees and burns.

**Validate Account**:

.. code-block:: lisp

    (defun validate-account (account:string) )

**Get Balance**:

.. code-block:: lisp

    (defun get-balance:decimal (account:string))
    10.0

**Exempt Accounts** from Fees and Burns:

.. code-block:: lisp

    (defun exempt-accounts:[string] (accounts:[string] revoked:bool))

Implementation Details
----------------------

The Heron token contract implements the ``fungible-v2`` and ``fungible-xchain-v1`` interfaces, providing standard functionalities for fungible tokens and cross-chain interoperability.

.. code-block:: lisp

    (implements fungible-v2)
    (implements fungible-xchain-v1)
