
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-retrives-a-list-of-servers-servers:

Retrives a list of servers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /servers

Retrieves list of all servers (only IDs, names, and links).

Servers contain a status attribute that indicates the current server state. You can filter on the server 				status when you complete a list servers request. The server status is returned in the response body.

For a full list of possible server status values, see.

For more information on the extended status extension ( ``OS-EXT-STS:power_state``, ``OS-EXT-STS:vm_state``, and ``OS-EXT-STS:task_state`` see.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200 203 300               |Success                  |Request succeeded.       |
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
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""






This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|changes-since             |Datetime *(Optional)*    |A time/date stamp for    |
|                          |                         |when the server last     |
|                          |                         |changed status.          |
+--------------------------+-------------------------+-------------------------+
|image                     |Uuid *(Optional)*        |The image reference for  |
|                          |                         |the desired image for    |
|                          |                         |your server instance.    |
+--------------------------+-------------------------+-------------------------+
|flavor                    |Uuid *(Optional)*        |The flavor reference for |
|                          |                         |the desired flavor for   |
|                          |                         |your server instance.    |
+--------------------------+-------------------------+-------------------------+
|name                      |Regexp *(Optional)*      |The name of the server,  |
|                          |                         |which can be queried     |
|                          |                         |with regular             |
|                          |                         |expressions. Notice that |
|                          |                         |?name=bob returns both   |
|                          |                         |"bob" and "bobbin". If   |
|                          |                         |you need to match only   |
|                          |                         |"bob", use a regular     |
|                          |                         |expression matching the  |
|                          |                         |syntax of the underlying |
|                          |                         |database server          |
|                          |                         |implemented for Cloud    |
|                          |                         |Servers (such as MySQL   |
|                          |                         |or PostgreSQL).          |
+--------------------------+-------------------------+-------------------------+
|marker                    |Uuid *(Optional)*        |The UUID of the server   |
|                          |                         |at which you want to set |
|                          |                         |a marker.                |
+--------------------------+-------------------------+-------------------------+
|limit                     |Int *(Optional)*         |The integer value used   |
|                          |                         |to limit the number of   |
|                          |                         |values which will be     |
|                          |                         |returned.                |
+--------------------------+-------------------------+-------------------------+
|status                    |Serverstatus *(Optional)*|The status of the        |
|                          |                         |server. For example, you |
|                          |                         |can filter on "ACTIVE".  |
|                          |                         |For a full list of       |
|                          |                         |possible status values,  |
|                          |                         |see                      |
+--------------------------+-------------------------+-------------------------+
|host                      |String *(Optional)*      |The name of the host.    |
+--------------------------+-------------------------+-------------------------+




This operation does not accept a request body.




**Example Retrives a list of servers: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json





Response
""""""""""""""""





This table shows the body parameters for the response:

+----------------------------+------------------------+------------------------+
|Name                        |Type                    |Description             |
+============================+========================+========================+
|parameters.servers.\ **id** |Uuid                    |The ID of the server.   |
+----------------------------+------------------------+------------------------+
|parameters.servers.\        |Uuid                    |An array of the self    |
|**links**                   |                        |and bookmark links to   |
|                            |                        |the server.             |
+----------------------------+------------------------+------------------------+
|parameters.servers.links.\  |Uuid                    |The URL for the server  |
|**href**                    |                        |and the associated      |
|                            |                        |``rel``.                |
+----------------------------+------------------------+------------------------+
|parameters.servers.links.\  |Uuid                    |The descriptive field   |
|**rel**                     |                        |for the associated      |
|                            |                        |``href``, which is      |
|                            |                        |either ``self`` or      |
|                            |                        |``bookmark``.           |
+----------------------------+------------------------+------------------------+
|parameters.servers.\        |String                  |The server name.        |
|**name**                    |                        |                        |
+----------------------------+------------------------+------------------------+
|parameters.\ **next**       |Anyuri                  |Moves to the next       |
|                            |                        |metadata item.          |
+----------------------------+------------------------+------------------------+
|parameters.\ **previous**   |Anyuri                  |Moves to the previous   |
|                            |                        |metadata item.          |
+----------------------------+------------------------+------------------------+







**Example Retrives a list of servers: JSON response**


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




