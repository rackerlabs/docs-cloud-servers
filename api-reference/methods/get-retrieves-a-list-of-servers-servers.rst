.. _get-retrieves-a-list-of-servers-servers:

Retrieve list of servers
------------------------

.. code::

    GET /servers

Retrieves list of all servers (only IDs, names, and links).

Servers contain a status attribute that indicates the current server state. You
can filter on the server status when you complete a list servers request. The
server status is returned in the response body.

For a full list of possible server status values including the extended status
extension ( ``OS-EXT-STS:power_state``, ``OS-EXT-STS:vm_state``, and
``OS-EXT-STS:task_state``),
see :ref:`Extended status extension <extended-status-extension>`.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200 203 300              |Success                  |Request succeeded.       |
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

This operation does not accept a request body.


**Example Retrieves list of servers: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


Response
^^^^^^^^


This table shows the body parameters for the response:

+----------------------------+-----------------------+------------------------+
|Name                        |Type                   |Description             |
+============================+=======================+========================+
|**servers**                 |Uuid                   |The array of server     |
|                            |                       |data.                   |
+----------------------------+-----------------------+------------------------+
|servers.\ **id**            |Uuid                   |The ID of the server.   |
+----------------------------+-----------------------+------------------------+
|servers.\  **links**        |Array                  |An array of the self    |
|                            |                       |and bookmark links to   |
|                            |                       |the server.             |
+----------------------------+-----------------------+------------------------+
|servers.links.\ **href**    |String                 |The URL for the server  |
|                            |                       |and the associated      |
|                            |                       |``rel``.                |
+----------------------------+-----------------------+------------------------+
|servers.links.\ **rel**     |String                 |The descriptive field   |
|                            |                       |for the associated      |
|                            |                       |``href``, which is      |
|                            |                       |either ``self`` or      |
|                            |                       |``bookmark``.           |
+----------------------------+-----------------------+------------------------+
|servers.\ **name**          |String                 |The server name.        |
|                            |                       |                        |
+----------------------------+-----------------------+------------------------+
|**next**                    |Anyuri                 |Moves to the next       |
|                            |                       |metadata item.          |
+----------------------------+-----------------------+------------------------+
|**previous**                |Anyuri                 |Moves to the previous   |
|                            |                       |metadata item.          |
+----------------------------+-----------------------+------------------------+


**Example Retrieves list of servers: JSON response**


.. code::

   Status Code: 200 OK
   Content-Length: 1024
   Content-Type: application/json
   Date: Wed, 03 Dec 2014 14:40:57 GMT
   Server: Jetty(8.0.y.z-SNAPSHOT)
   Via: 1.1 Repose (Repose/2.12)
   x-compute-request-id: req-fda78f69-d934-4ed3-a5b8-255894baa6aa


.. code::

   {
     "servers": [
       {
         "id": "8f64d643-f48a-459c-a7af-717dfc7580ee",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/v2/123456/servers/8f64d643-f48a-459c-a7af-717dfc7580ee",
             "rel": "self"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/123456/servers/8f64d643-f48a-459c-a7af-717dfc7580ee",
             "rel": "bookmark"
           }
         ],
         "name": "wordpress.myveryown.com"
       },
       {
         "id": "5bccf43e-35fa-4d65-9390-2b2d6b23ec89",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/v2/123456/servers/5bccf43e-35fa-4d65-9390-2b2d6b23ec89",
             "rel": "self"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/123456/servers/5bccf43e-35fa-4d65-9390-2b2d6b23ec89",
             "rel": "bookmark"
           }
         ],
         "name": "DB2"
       },
       {
         "id": "d40dcb7f-2268-4fff-a592-b1944413f983",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/v2/123456/servers/d40dcb7f-2268-4fff-a592-b1944413f983",
             "rel": "self"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/123456/servers/d40dcb7f-2268-4fff-a592-b1944413f983",
             "rel": "bookmark"
           }
         ],
         "name": "Branwen"
       }
     ]
   }




