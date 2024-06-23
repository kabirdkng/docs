KX API User Documentation
=========================

.. contents:: Table of Contents
   :depth: 2

Introduction
------------

Welcome to the KX API! This documentation provides all the information you need to interact with the API.

Endpoints
---------

1. Create DAO
2. Add Member to DAO
3. Add Admin to DAO
4. Assign Custom Role
5. Update Member in DAO
6. Update Admin in DAO
7. Delete Member from DAO
8. Delete Admin from DAO
9. Get DAO Info
10. Get DAOs
11. Create Poll
12. Get Poll Results
13. Get Stored Polls
14. Cast Vote
15. Get Twitter ID by Username
16. Register
17. Twitter Callback
18. Check Session Status

Create DAO
----------

**Endpoint:** `POST /dao/create`

**Description:** Create a new DAO.

**Request:**

.. code-block:: json

    {
        "name": "DAO Name",
        "admin": {
            "twitterId": "adminTwitterId",
            "twitterUsername": "adminUsername"
        }
    }

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "members": [
            {
                "twitterId": "adminTwitterId",
                "twitterUsername": "adminUsername"
            }
        ],
        "admins": [
            {
                "twitterId": "adminTwitterId",
                "twitterUsername": "adminUsername"
            }
        ],
        "customRoles": [],
        "pendingVotes": []
    }

Add Member to DAO
-----------------

**Endpoint:** `POST /dao/add-member`

**Description:** Add a member to a DAO.

**Request:**

.. code-block:: json

    {
        "daoId": "DAO ID",
        "members": [
            {
                "twitterId": "memberTwitterId",
                "twitterUsername": "memberUsername"
            }
        ]
    }

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "members": [
            {
                "twitterId": "adminTwitterId",
                "twitterUsername": "adminUsername"
            },
            {
                "twitterId": "memberTwitterId",
                "twitterUsername": "memberUsername"
            }
        ],
        "admins": [
            {
                "twitterId": "adminTwitterId",
                "twitterUsername": "adminUsername"
            }
        ],
        "customRoles": [],
        "pendingVotes": []
    }

Add Admin to DAO
----------------

**Endpoint:** `POST /dao/add-admin`

**Description:** Add an admin to a DAO.

**Request:**

.. code-block:: json

    {
        "daoId": "DAO ID",
        "admins": [
            {
                "twitterId": "adminTwitterId",
                "twitterUsername": "adminUsername"
            }
        ]
    }

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "members": [...],
        "admins": [
            {
                "twitterId": "adminTwitterId",
                "twitterUsername": "adminUsername"
            }
        ],
        ...
    }

Assign Custom Role
------------------

**Endpoint:** `POST /dao/assign-role`

**Description:** Assign a custom role to a member in a DAO.

**Request:**

.. code-block:: json

    {
        "daoId": "DAO ID",
        "memberTwitterUsername": "memberUsername",
        "roleName": "Role Name",
        "permissions": ["Permission1", "Permission2"]
    }

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "members": [
            {
                "twitterId": "memberTwitterId",
                "twitterUsername": "memberUsername",
                "customRole": {
                    "roleName": "Role Name",
                    "permissions": ["Permission1", "Permission2"]
                }
            }
        ],
        ...
    }

Update Member in DAO
--------------------

**Endpoint:** `PUT /dao/update-member`

**Description:** Update a member's information in a DAO.

**Request:**

.. code-block:: json

    {
        "daoId": "DAO ID",
        "member": {
            "twitterId": "memberTwitterId",
            "twitterUsername": "memberUsername",
            "customRole": {
                "roleName": "Role Name",
                "permissions": ["Permission1", "Permission2"]
            }
        }
    }

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "members": [
            {
                "twitterId": "memberTwitterId",
                "twitterUsername": "memberUsername",
                "customRole": {
                    "roleName": "Role Name",
                    "permissions": ["Permission1", "Permission2"]
                }
            }
        ],
        ...
    }

Update Admin in DAO
-------------------

**Endpoint:** `PUT /dao/update-admin`

**Description:** Update an admin's information in a DAO.

**Request:**

.. code-block:: json

    {
        "daoId": "DAO ID",
        "admin": {
            "twitterId": "adminTwitterId",
            "twitterUsername": "adminUsername"
        }
    }

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "admins": [
            {
                "twitterId": "adminTwitterId",
                "twitterUsername": "adminUsername"
            }
        ],
        ...
    }

Delete Member from DAO
----------------------

**Endpoint:** `DELETE /dao/delete-member`

**Description:** Delete a member from a DAO.

**Request:**

.. code-block:: json

    {
        "daoId": "DAO ID",
        "twitterUsername": "memberUsername"
    }

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "members": [...],
        ...
    }

Delete Admin from DAO
---------------------

**Endpoint:** `DELETE /dao/delete-admin`

**Description:** Delete an admin from a DAO.

**Request:**

.. code-block:: json

    {
        "daoId": "DAO ID",
        "twitterUsername": "adminUsername"
    }

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "admins": [...],
        ...
    }

Get DAO Info
------------

**Endpoint:** `GET /dao/:daoName`

**Description:** Get information about a specific DAO.

**Request:**

.. code-block:: bash

    GET /dao/DAO_NAME

**Response:**

.. code-block:: json

    {
        "_id": "daoId",
        "name": "DAO Name",
        "members": [...],
        "admins": [...],
        "customRoles": [...],
        "pendingVotes": [...]
    }

Get DAOs
--------

**Endpoint:** `GET /daos`

**Description:** Get a list of all DAOs.

**Request:**

.. code-block:: bash

    GET /daos

**Response:**

.. code-block:: json

    [
        {
            "_id": "daoId1",
            "name": "DAO Name 1",
            ...
        },
        {
            "_id": "daoId2",
            "name": "DAO Name 2",
            ...
        }
    ]

Create Poll
-----------

**Endpoint:** `POST /polls/create`

**Description:** Create a new Twitter poll.

**Request:**

.. code-block:: json

    {
        "question": "Poll question",
        "choices": ["Option 1", "Option 2"],
        "durationMinutes": 60,
        "method": "reply_all",
        "daoId": "DAO ID"
    }

**Response:**

.. code-block:: json

    {
        "_id": "pollId",
        "question": "Poll question",
        "choices": ["Option 1", "Option 2"],
        "durationMinutes": 60,
        ...
    }

Get Poll Results
----------------

**Endpoint:** `GET /polls/results/:pollId`

**Description:** Get the results of a specific Twitter poll.

**Request:**

.. code-block:: bash

    GET /polls/results/POLL_ID

**Response:**

.. code-block:: json

    {
        "_id": "pollId",
        "question": "Poll question",
        "choices": ["Option 1", "Option 2"],
        "votes": [
            {
                "userId": "userId1",
                "choice": "Option 1"
            },
            ...
        ]
    }

Get Stored Polls
----------------

**Endpoint:** `GET /polls/stored`

**Description:** Get a list of all stored polls.

**Request:**

.. code-block:: bash

    GET /polls/stored

**Response:**

.. code-block:: json

    [
        {
            "_id": "pollId1",
            "question": "Poll question 1",
            "choices": ["Option 1", "Option 2"],
            ...
        },
        {
            "_id": "pollId2",
            "question": "Poll question 2",
            "choices": ["Option 1", "Option 2"],
            ...
        }
    ]

Cast Vote
---------

**Endpoint:** `POST /polls/cast-vote`

**Description:** Cast a vote in a poll.

**Request:**

.. code-block:: json

    {
        "pollId": "POLL_ID",
        "choice": "Option 1",
        "userId": "USER_ID",
        "daoName": "DAO Name"
    }

**Response:**

.. code-block:: json

    {
        "message": "Vote cast successfully"
    }

Get Twitter ID by Username
--------------------------

**Endpoint:** `POST /polls/twitter-id`

**Description:** Get Twitter ID(s) by username(s).

**Request:**

.. code-block:: json

    {
        "usernames": ["username1", "username2"]
    }

**Response:**

.. code-block:: json

    [
        {
            "username": "username1",
            "id": "twitterId1"
        },
        {
            "username": "username2",
            "id": "twitterId2"
        }
    ]

Register
--------

**Endpoint:** `POST /register`

**Description:** Register a new user.

**Request:**

.. code-block:: bash

    POST /register

**Response:**

.. code-block:: json

    {
        "message": "User registered successfully"
    }

Twitter Callback
----------------

**Endpoint:** `GET /twitter/callback`

**Description:** Twitter OAuth callback.

**Request:**

.. code-block:: bash

    GET /twitter/callback

**Response:**

.. code-block:: json

    {
        "message": "Twitter callback successful"
    }

Check Session Status
--------------------

**Endpoint:** `GET /status`

**Description:** Check the session status of the user.

**Request:**

.. code-block:: bash

    GET /status

**Response:**

.. code-block:: json

    {
        "authenticated": true,
        "user": {
            "id": "userId",
            ...
        }
    }
