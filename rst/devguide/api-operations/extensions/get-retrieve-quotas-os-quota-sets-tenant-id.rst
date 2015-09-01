
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve quotas
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /os-quota-sets/{tenant_id}

Retrieve quotas for specified tenant.

This operation shows current quotas for a tenant.

In the URI, specify the tenant ID.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200 203                   |Success                  |Request succeeded.       |
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
|{tenant_id}               |String                   |The tenant id.           |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Retrieve quotas: JSON request**


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
|quota-set                 |Object                   |The container of quota-  |
|                          |                         |sets.                    |
+--------------------------+-------------------------+-------------------------+
|ram                       |Int                      |The quota for ram.       |
+--------------------------+-------------------------+-------------------------+
|instances                 |Uuid                     |The quota for instances. |
+--------------------------+-------------------------+-------------------------+
|metadata-items            |Uuid                     |The quota for metadata-  |
|                          |                         |items.                   |
+--------------------------+-------------------------+-------------------------+





**Example Retrieve quotas: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 513
        Content-Type: application/json
        Date: Fri, 10 Jul 2015 17:33:12 GMT, Fri, 10 Jul 2015 17:33:12 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-01fb912a-5a59-4ac1-80d6-368c2a2e0df8


