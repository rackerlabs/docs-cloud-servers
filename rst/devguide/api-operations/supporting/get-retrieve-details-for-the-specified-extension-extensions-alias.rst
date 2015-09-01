
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve details for the specified extension
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /extensions/{alias}

Retrieves a specified extension's details.

An unavailable extension issues an ``itemNotFound (404)`` response.



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

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{alias}                   |Uuid                     |The alias, which is a    |
|                          |                         |name for a pointer to a  |
|                          |                         |resource. For example, a |
|                          |                         |named extension.         |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Retrieve details for the specified extension: JSON request**


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
|extension                 |Object                   |The container of         |
|                          |                         |extensions attributes.   |
+--------------------------+-------------------------+-------------------------+
|updated                   |Date                     |The most recent update   |
|                          |                         |date for the extension.  |
+--------------------------+-------------------------+-------------------------+
|name                      |String                   |The name of the          |
|                          |                         |extension.               |
+--------------------------+-------------------------+-------------------------+
|links                     |Array                    |The array of links for   |
|                          |                         |the extension.           |
+--------------------------+-------------------------+-------------------------+
|namespace                 |String                   |The namespace of the     |
|                          |                         |extension.               |
+--------------------------+-------------------------+-------------------------+
|alias                     |String                   |The alias, or short      |
|                          |                         |name, of the extension.  |
+--------------------------+-------------------------+-------------------------+
|description               |String                   |The description of the   |
|                          |                         |extension.               |
+--------------------------+-------------------------+-------------------------+





**Example Retrieve details for the specified extension: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 257
        Content-Type: application/json
        Date: Fri, 10 Jul 2015 19:56:53 GMT, Fri, 10 Jul 2015 19:56:54 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-d612f98f-d446-493c-a1ba-6869828f8a80


