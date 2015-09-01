
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve list of key pairs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /os-keypairs

Retrieves the current rate limits and absolute limits for your account.

This operation retrieves a list of server key pairs.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Success                  |Request succeeded.       |
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






This operation does not accept a request body.




Response
""""""""""""""""


This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|keypairs                  |Array                    |An array of key pairs.   |
+--------------------------+-------------------------+-------------------------+
|keypairs                  |Object                   |A container of key pair  |
|                          |                         |details.                 |
+--------------------------+-------------------------+-------------------------+
|fingerprint               |String                   |A short sequence of      |
|                          |                         |bytes used to            |
|                          |                         |authenticate, or look    |
|                          |                         |up, a longer public key. |
+--------------------------+-------------------------+-------------------------+
|name                      |String                   |The name of the key pair.|
+--------------------------+-------------------------+-------------------------+
|public_key                |String                   |The public ssh key value.|
+--------------------------+-------------------------+-------------------------+





**Example Retrieve list of key pairs: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 540
        Content-Type: application/json
        Date: Thu, 02 Apr 2015 18:09:36 GMT, Thu, 02 Apr 2015 18:09:36 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-5a9c3b9d-67cf-4b7f-b31d-0670e1c667a0


