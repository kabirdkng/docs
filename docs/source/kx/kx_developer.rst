KX API Developer Documentation
==============================

.. contents:: Table of Contents
   :depth: 2

API Endpoints
-------------

.. _create_dao:

Create DAO
~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X POST {apiHost}/dao/create \
    -H "Content-Type: application/json" \
    -d '{
        "name": "DAO Name",
        "admin": {
            "twitterId": "adminTwitterId",
            "twitterUsername": "adminUsername"
        }
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const createDAO = async () => {
        try {
            const response = await axios.post('{apiHost}/dao/create', {
                name: "DAO Name",
                admin: {
                    twitterId: "adminTwitterId",
                    twitterUsername: "adminUsername"
                }
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    createDAO();

Add Member to DAO
~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X POST {apiHost}/dao/add-member \
    -H "Content-Type: application/json" \
    -d '{
        "daoId": "DAO ID",
        "members": [
            {
                "twitterId": "memberTwitterId",
                "twitterUsername": "memberUsername"
            }
        ]
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const addMemberToDAO = async () => {
        try {
            const response = await axios.post('{apiHost}/dao/add-member', {
                daoId: "DAO ID",
                members: [
                    {
                        twitterId: "memberTwitterId",
                        twitterUsername: "memberUsername"
                    }
                ]
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    addMemberToDAO();

Add Admin to DAO
~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X POST {apiHost}/dao/add-admin \
    -H "Content-Type: application/json" \
    -d '{
        "daoId": "DAO ID",
        "admins": [
            {
                "twitterId": "adminTwitterId",
                "twitterUsername": "adminUsername"
            }
        ]
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const addAdminToDAO = async () => {
        try {
            const response = await axios.post('{apiHost}/dao/add-admin', {
                daoId: "DAO ID",
                admins: [
                    {
                        twitterId: "adminTwitterId",
                        twitterUsername: "adminUsername"
                    }
                ]
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    addAdminToDAO();

Assign Custom Role
~~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X POST {apiHost}/dao/assign-role \
    -H "Content-Type: application/json" \
    -d '{
        "daoId": "DAO ID",
        "memberTwitterUsername": "memberUsername",
        "roleName": "Role Name",
        "permissions": ["Permission1", "Permission2"]
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const assignCustomRole = async () => {
        try {
            const response = await axios.post('{apiHost}/dao/assign-role', {
                daoId: "DAO ID",
                memberTwitterUsername: "memberUsername",
                roleName: "Role Name",
                permissions: ["Permission1", "Permission2"]
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    assignCustomRole();

Update Member in DAO
~~~~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X PUT {apiHost}/dao/update-member \
    -H "Content-Type: application/json" \
    -d '{
        "daoId": "DAO ID",
        "member": {
            "twitterId": "memberTwitterId",
            "twitterUsername": "memberUsername",
            "customRole": {
                "roleName": "Role Name",
                "permissions": ["Permission1", "Permission2"]
            }
        }
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const updateMemberInDAO = async () => {
        try {
            const response = await axios.put('{apiHost}/dao/update-member', {
                daoId: "DAO ID",
                member: {
                    twitterId: "memberTwitterId",
                    twitterUsername: "memberUsername",
                    customRole: {
                        roleName: "Role Name",
                        permissions: ["Permission1", "Permission2"]
                    }
                }
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    updateMemberInDAO();

Update Admin in DAO
~~~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X PUT {apiHost}/dao/update-admin \
    -H "Content-Type: application/json" \
    -d '{
        "daoId": "DAO ID",
        "admin": {
            "twitterId": "adminTwitterId",
            "twitterUsername": "adminUsername"
        }
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const updateAdminInDAO = async () => {
        try {
            const response = await axios.put('{apiHost}/dao/update-admin', {
                daoId: "DAO ID",
                admin: {
                    twitterId: "adminTwitterId",
                    twitterUsername: "adminUsername"
                }
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    updateAdminInDAO();

Delete Member from DAO
~~~~~~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X DELETE {apiHost}/dao/delete-member \
    -H "Content-Type: application/json" \
    -d '{
        "daoId": "DAO ID",
        "twitterUsername": "memberUsername"
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const deleteMemberFromDAO = async () => {
        try {
            const response = await axios.delete('{apiHost}/dao/delete-member', {
                data: {
                    daoId: "DAO ID",
                    twitterUsername: "memberUsername"
                }
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    deleteMemberFromDAO();

Delete Admin from DAO
~~~~~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X DELETE {apiHost}/dao/delete-admin \
    -H "Content-Type: application/json" \
    -d '{
        "daoId": "DAO ID",
        "twitterUsername": "adminUsername"
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const deleteAdminFromDAO = async () => {
        try {
            const response = await axios.delete('{apiHost}/dao/delete-admin', {
                data: {
                    daoId: "DAO ID",
                    twitterUsername: "adminUsername"
                }
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    deleteAdminFromDAO();

Get DAO Info
~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X GET {apiHost}/dao/DAO_NAME

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const getDaoInfo = async (daoName) => {
        try {
            const response = await axios.get(`{apiHost}/dao/${daoName}`);
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    getDaoInfo('DAO_NAME');

Get DAOs
~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X GET {apiHost}/daos

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const getDAOs = async () => {
        try {
            const response = await axios.get('{apiHost}/daos');
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    getDAOs();

Create Poll
~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X POST {apiHost}/polls/create \
    -H "Content-Type: application/json" \
    -d '{
        "question": "Poll question",
        "choices": ["Option 1", "Option 2"],
        "durationMinutes": 60,
        "method": "reply_all",
        "daoId": "DAO ID"
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const createPoll = async () => {
        try {
            const response = await axios.post('{apiHost}/polls/create', {
                question: "Poll question",
                choices: ["Option 1", "Option 2"],
                durationMinutes: 60,
                method: "reply_all",
                daoId: "DAO ID"
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    createPoll();

Get Poll Results
~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X GET {apiHost}/polls/results/POLL_ID

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const getPollResults = async (pollId) => {
        try {
            const response = await axios.get(`{apiHost}/polls/results/${pollId}`);
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    getPollResults('POLL_ID');

Get Stored Polls
~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X GET {apiHost}/polls/stored

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const getStoredPolls = async () => {
        try {
            const response = await axios.get('{apiHost}/polls/stored');
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    getStoredPolls();

Cast Vote
~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X POST {apiHost}/polls/cast-vote \
    -H "Content-Type: application/json" \
    -d '{
        "pollId": "POLL_ID",
        "choice": "Option 1",
        "userId": "USER_ID",
        "daoName": "DAO Name"
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const castVote = async () => {
        try {
            const response = await axios.post('{apiHost}/polls/cast-vote', {
                pollId: "POLL_ID",
                choice: "Option 1",
                userId: "USER_ID",
                daoName: "DAO Name"
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    castVote();

Get Twitter ID by Username
~~~~~~~~~~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X POST {apiHost}/polls/twitter-id \
    -H "Content-Type: application/json" \
    -d '{
        "usernames": ["username1", "username2"]
    }'

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const getTwitterIdByUsername = async () => {
        try {
            const response = await axios.post('{apiHost}/polls/twitter-id', {
                usernames: ["username1", "username2"]
            });
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    getTwitterIdByUsername();

Register
~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X POST {apiHost}/register

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const registerUser = async () => {
        try {
            const response = await axios.post('{apiHost}/register');
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    registerUser();

Get Twitter Callback
~~~~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X GET {apiHost}/twitter/callback

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const getTwitterCallback = async () => {
        try {
            const response = await axios.get('{apiHost}/twitter/callback');
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    getTwitterCallback();

Check Session Status
~~~~~~~~~~~~~~~~~~~~

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

**cURL Example:**

.. code-block:: bash

    curl -X GET {apiHost}/status

**Node.js Example:**

.. code-block:: javascript

    const axios = require('axios');

    const checkSessionStatus = async () => {
        try {
            const response = await axios.get('{apiHost}/status');
            console.log(response.data);
        } catch (error) {
            console.error(error);
        }
    };

    checkSessionStatus();
