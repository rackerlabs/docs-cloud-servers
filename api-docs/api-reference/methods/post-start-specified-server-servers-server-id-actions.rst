.. _post-start-specified-server-servers-server-id-actions:

Start specified server
----------------------

.. code::

    POST /servers/{server_id}/action

This operation starts a stopped server, and changes its status to ``ACTIVE``.

.. note::

   Prior to running this command, the server status must be  ``SHUTTOFF``.

   If the server status is ``LOCKED``, you must have administrator privileges
   to start the server.


This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|202                      |Success                  |Request succeeded.       |
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

This table shows the URI parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+


This table shows the body parameters for the request:

+--------------------------+----------------------+---------------------------+
|Name                      |Type                  |Description                |
+==========================+======================+===========================+
| **os-start**             |Object                |Specification of the       |
|                          |                      |start action for the       |
|                          |                      |specified server. The key  |
|                          |                      |pair value is always null. |
+--------------------------+----------------------+---------------------------+

**Example Start specified server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "os-start" : null
   }


Response
^^^^^^^^

This operation does not return a response body.

**Example Start specified server: JSON response**


.. code::

       Status Code: 202 OK
       Content-Length: 1250
       Content-Type: application/json
       Date: Thu, 10 Dec 2014 19:43:18 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-8c905dfe-2c9a-17e5-8e53-4478e2813c75

