.. _post-migrate-server-server-id-actions:

Migrate specified server
------------------------

.. code::

    POST /servers/{server_id}/action
    
This operation migrates the server to a different hypervisor host within the
Rackspace Cloud in the same region without changing the server's data and IP
addresses.

During a migration, the server's status changes to **RESIZING** because the
migration function uses the resize operation to migrate the server. The original
server is saved for 24 hours to allow rollback. You should test and explicitly
confirm all migrations. After you confirm, the original server is removed. If
you do not explicitly confirm or revert the migration, all migrations are
automatically confirmed after 24 hours 

.. note::
   This operation is not available for OnMetal servers.

Specify the target server ID in the URI.

In the request body, specify the ``migrate`` action followed by attributes.

This table shows the possible response codes for this operation:

+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|202                      |Successful               |Request succeeded.       |
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

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**migrate**               |Object                  |Specification of the     |
|                          |                        |migrate action for the   |
|                          |                        |specified server.        |
+--------------------------+------------------------+-------------------------+


**Example migrate specified server: JSON request**

.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json

.. code::

   {
       "migrate" : {
       }
   }


Response
^^^^^^^^

**Example Migrate specified server: JSON response**


.. code::

   Status Code: 202 No Content
   Content-Length: 0
   Content-Type: application/json
   Date: Thu, 04 Dec 2014 21:45:47 GMT
   Server: Jetty(8.0.y.z-SNAPSHOT)
   Via: 1.1 Repose (Repose/2.12)
   x-compute-request-id
