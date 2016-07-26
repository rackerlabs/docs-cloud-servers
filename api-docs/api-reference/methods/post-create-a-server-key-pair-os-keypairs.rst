.. _post-create-a-server-key-pair-os-keypairs:

Create a server key pair
------------------------

.. code::

    POST /os-keypairs

Creates a server key pair

Creates a key pair, with the name specified in the request body, to associate
with a new server instance.

.. important::
   Key Pair Naming Rules

   The key name must be unique and may not exceed 255 characters. It can contain
   the following characters:

   * alphanumeric
   * spaces
   * dashes
   * underscores



This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200                      |Success                  |Request accepted.        |
+-------------------------+-------------------------+-------------------------+
|400                      |Error                    |A general error has      |
|                         |                         |occured.                 |
+-------------------------+-------------------------+-------------------------+
|401                      |Unauthorized             |Unauthorized.            |
+-------------------------+-------------------------+-------------------------+
|403                      |Forbidden                |Forbidden.               |
+-------------------------+-------------------------+-------------------------+
|405                      |Bad Method               |Bad method.              |
+-------------------------+-------------------------+-------------------------+
|409                      |Conflicting Reqest       |Conflicting request.     |
+-------------------------+-------------------------+-------------------------+
|413                      |Over Limit               |The number of items      |
|                         |                         |returned is above the    |
|                         |                         |allowed limit.           |
+-------------------------+-------------------------+-------------------------+
|500                      |API Fault                |API fault.               |
+-------------------------+-------------------------+-------------------------+
|503                      |Service Unavailable      |The requested service is |
|                         |                         |unavailable.             |
+-------------------------+-------------------------+-------------------------+


Request
^^^^^^^


This table shows the body parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**keypair**               |Object                  |The container for the    |
|                          |                        |key pair request.        |
+--------------------------+------------------------+-------------------------+
|keypair.\ **name**        |String                  |The name to associate    |
|                          |                        |with the key pair.       |
+--------------------------+------------------------+-------------------------+

**Example Create a server key pair: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
      "keypair":{
           "name":"name_of_keypair"
       }
   }

Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**keypair**               |Object                  |The container for the    |
|                          |                        |key pair details.        |
+--------------------------+------------------------+-------------------------+
|keypair.\ **fingerprint** |String                  |A short sequence of      |
|                          |                        |bytes used to            |
|                          |                        |authenticate, or look    |
|                          |                        |up, a longer public key. |
+--------------------------+------------------------+-------------------------+
|keypair.\ **name**        |String                  |The name of the key pair.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|keypair.\ **private_key** |String                  |The private ssh key      |
|                          |                        |value.                   |
+--------------------------+------------------------+-------------------------+
|keypair.\ **public_key**  |String                  |The public ssh key value.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|keypair.\  **user_id**    |String                  |The ID of the user.      |
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+


**Example Create a server key pair: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 2270
       Content-Type: application/json
       Date: Thu, 02 Apr 2015 17:54:20 GMT, Thu, 02 Apr 2015 17:54:21 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-2611a666-6693-46e0-a635-54c506eb7513


.. code::

   {
       "keypair": {
           "fingerprint": "35:9d:d0:c3:4a:80:d3:d8:86:f1:ca:f7:df:c4:f9:d8",
           "name": "name_of_keypair",
           "private_key": "-----BEGIN RSA PRIVATE KEY-----\nMIICXAIBAAKBgQC9mC3WZN9UGLxgPBpP7H5jZMc6pKwOoSgre8yun6REFktn/Kz7\nDUt9jaR1UJyRzHxITfCfAIgSxPdGqB/oF1suMyWgu5i0625vavLB5z5kC8Hq3qZJ\n9zJO1poE1kyD+htiTtPWJ88e12xuH2XB/CZN9OpEiF98hAagiOE0EnOS5QIDAQAB\nAoGAE5XO1mDhORy9COvsg+kYPUhB1GsCYxh+v88wG7HeFDKBY6KUc/Kxo6yoGn5T\nTjRjekyi2KoDZHz4VlIzyZPwFS4I1bf3oCunVoAKzgLdmnTtvRNMC5jFOGc2vUgP\n9bSyRj3S1R4ClVk2g0IDeagko/jc8zzLEYuIK+fbkds79YECQQDt3vcevgegnkga\ntF4NsDmmBPRkcSHCqrANP/7vFcBQN3czxeYYWX3DK07alu6GhH1Y4sHbdm616uU0\nll7xbDzxAkEAzAtN2IyftNygV2EGiaGgqLyo/tD9+Vui2qCQplqe4jvWh/5Sparl\nOjmKo+uAW+hLrLVMnHzRWxbWU8hirH5FNQJATO+ZxCK4etXXAnQmG41NCAqANWB2\nB+2HJbH2NcQ2QHvAHUm741JGn/KI/aBlo7KEjFRDWUVUB5ji64BbUwCsMQJBAIku\nLGcjnBf/oLk+XSPZC2eGd2Ph5G5qYmH0Q2vkTx+wtTn3DV+eNsDfgMtWAJVJ5t61\ngU1QSXyhLPVlKpnnxuUCQC+xvvWjWtsLaFtAsZywJiqLxQzHts8XLGZptYJ5tLWV\nrtmYtBcJCN48RrgQHry/xWYeA4K/AFQpXfNPgprQ96Q=\n-----END RSA PRIVATE KEY-----\n",
           "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQC9mC3WZN9UGLxgPBpP7H5jZMc6pKwOoSgre8yun6REFktn/Kz7DUt9jaR1UJyRzHxITfCfAIgSxPdGqB/oF1suMyWgu5i0625vavLB5z5kC8Hq3qZJ9zJO1poE1kyD+htiTtPWJ88e12xuH2XB/CZN9OpEiF98hAagiOE0EnOS5Q== Generated by Nova\n",
           "user_id": "fake"
       }
   }




