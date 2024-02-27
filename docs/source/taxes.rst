Tax Processing Contract Functions
=================================

**Contract / Module:**
  * taxes

This module manages tax-related operations, including updating costs, processing payments, and managing accounts within the Kadena blockchain environment.

Main Functions
--------------

update-costs
~~~~~~~~~~~~
Updates the cost associated with a specific year.

* **Parameters**:
  - ``year``: The tax year as a string.
  - ``cost``: The cost associated with the year, as a decimal.

* **Returns**: ``string`` indicating the update status.

.. code:: lisp

  pact> (update-costs "2023" 100.00)
  "Write succeeded"

get-costs
~~~~~~~~~
Retrieves all cost entries.

* **Returns**: A list of objects of type ``cost-schema``, each representing a year and its associated cost.

.. code-block:: lisp

  pact> (get-costs)
  [
   {"cost": 10.0,"year": "2019"}
   {"cost": 10.0,"year": "2020"}
   {"cost": 10.0,"year": "2021"}
   {"cost": 10.0,"year": "2022"}
   {"cost": 10.0,"year": "2023"}
   {"cost": 10.0,"year": "2024"}
  ]

process-payment
~~~~~~~~~~~~~~~
Processes a tax payment for a specific year and account, transferring the required funds.

* **Parameters**:
  - ``year``: The tax year as a string.
  - ``account``: The account name as a string.
  - ``guard``: The guard associated with the account.

* **Returns**: ``bool`` indicating success or failure of the payment processing.

.. code:: lisp

  pact> (process-payment "2023" "alice" (read-keyset "alice-guard"))
  true

process-secondary-payment
~~~~~~~~~~~~~~~~~~~~~~~~~
Processes a payment for a secondary account for tax purposes.

* **Parameters**:
  - ``year``: The tax year as a string.
  - ``account``: The primary account name as a string.
  - ``guard``: The guard associated with the primary account.
  - ``secondaryAccount``: The secondary account name as a string.

* **Returns**: ``bool`` indicating success or failure of the secondary payment processing.

.. code:: lisp

  pact> (process-secondary-payment "2023" "alice" (read-keyset "alice-guard") "alice-secondary")
  true

get-payment-amount
~~~~~~~~~~~~~~~~~~
Retrieves the payment amount for a specific year.

* **Parameters**:
  - ``year``: The tax year as a string.

* **Returns**: ``decimal`` representing the cost for the specified year.

.. code:: lisp

  pact> (get-payment-amount "2023")
  10.0

transfer-funds
~~~~~~~~~~~~~~
Transfers funds from a designated BANK account to a specified account.

* **Parameters**:
  - ``account``: The account name to transfer funds to, as a string.
  - ``guard``: The guard associated with the account.
  - ``amount``: The amount to transfer, as a decimal.

* **Returns**: ``string`` indicating the transfer status.

.. code:: lisp

  pact> (transfer-funds "alice" (read-keyset "alice-guard") 50.00)
  "Write succeeded"