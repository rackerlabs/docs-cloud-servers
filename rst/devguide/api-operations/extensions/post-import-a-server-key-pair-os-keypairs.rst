
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Import a server key pair
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /os-keypairs

Import a server key pair

Imports, or uploads, a key pair, with the name and public key specified in the request body, to associate 				with a new server instance.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Success                  |Request accepted.        |
+--------------------------+-------------------------+-------------------------+
|400                       |Error                    |A general error has      |
|                          |                         |occured.                 |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |Unauthorized.            |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Forbidden.               |
+--------------------------+-------------------------+-------------------------+
|405                       |Bad Method               |Bad method.              |
+--------------------------+-------------------------+-------------------------+
|409                       |Conflicting Reqest       |Conflicting request.     |
+--------------------------+-------------------------+-------------------------+
|413                       |Over Limit               |The number of items      |
|                          |                         |returned is above the    |
|                          |                         |allowed limit.           |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""






This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|keypair                   |Object *(Required)*      |The container for the    |
|                          |                         |key pair request.        |
+--------------------------+-------------------------+-------------------------+
|name                      |String *(Required)*      |The name to associate    |
|                          |                         |with the key pair.       |
+--------------------------+-------------------------+-------------------------+
|public_key                |String *(Required)*      |The public ssh key value.|
+--------------------------+-------------------------+-------------------------+





**Example Import a server key pair: JSON request**


.. code::

    X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
    Content-Type: application/json
    Accept: application/json


Response
""""""""""""""""


This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|keypair                   |Object                   |The container for the    |
|                          |                         |key pair details.        |
+--------------------------+-------------------------+-------------------------+
|fingerprint               |String                   |A short sequence of      |
|                          |                         |bytes used to            |
|                          |                         |authenticate, or look    |
|                          |                         |up, a longer public key. |
+--------------------------+-------------------------+-------------------------+
|name                      |String                   |The name of the key pair.|
+--------------------------+-------------------------+-------------------------+
|private_key               |String                   |The private ssh key      |
|                          |                         |value.                   |
+--------------------------+-------------------------+-------------------------+
|public_key                |String                   |The public ssh key value.|
+--------------------------+-------------------------+-------------------------+
|user_id                   |String                   |The ID of the user.      |
+--------------------------+-------------------------+-------------------------+





**Example Import a server key pair: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 545
        Content-Type: application/json
        Date: Thu, 02 Apr 2015 18:08:19 GMT, Thu, 02 Apr 2015 18:08:19 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-9efa9191-4f08-4d65-92c7-acd934e5c5b0


