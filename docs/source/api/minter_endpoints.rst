Minter Endpoints
================

This section details the endpoints related to minting operations, including standard minting and any other related functionalities.

Standard Minting Operation
--------------------------

.. http:post:: /api/0/v2minter/standard

   Mints a new token with the provided image and metadata. Authentication is required and is done via cookies.

   **Request Body**

   :<json string account: The account to mint the token for.
   :<json string policy: The policy to use for minting.
   :<json file image: The image file to mint with the token.
   :<json object metadata: (Optional) Additional metadata for the token in JSON format.

   **Responses**

   :status 200: A successful minting operation. Returns the token ID and metadata hash.
   :status 400: Bad request, possibly due to missing file upload or insufficient credits.
   :status 500: Error during the minting process or internal server error.
