.. _post-stop-specified-server-servers-server-id-actions:

Stop specified server
---------------------

.. code::

    POST /servers/{server_id}/action

This operation stops a running server, and changes the server status to
``SHUTOFF`` and changes the clean_shutdown parameter to ``TRUE``.

.. note::

   Prior to running this command, the server status must be either ``ACTIVE``
   or ``ERROR``.

   If the server status is ``LOCKED``, you must have administrator privileges
   to stop the server.

.. warning::

   The owner of the server will continue to be billed even if a server is
   stopped. To stop getting billed, delete the server

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
| **os-stop**              |Object                |Specification of the       |
|                          |                      |stop action for the        |
|                          |                      |specified server. The key  |
|                          |                      |pair value is always null. |
+--------------------------+----------------------+---------------------------+

**Example Stop specified server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "os-stop" : null
   }


Response
^^^^^^^^

This operation does not return a response body.

**Example Stop specified server: JSON response**


.. code::

       Status Code: 202 OK
       Content-Length: 1250
       Content-Type: application/json
       Date: Thu, 10 Dec 2014 19:43:18 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-8c905dfe-2c9a-17e5-8e53-4478e2813c75




