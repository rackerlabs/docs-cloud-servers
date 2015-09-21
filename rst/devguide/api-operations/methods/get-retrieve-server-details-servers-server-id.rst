
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-retrieve-server-details-servers-server-id:

Retrieve server details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /servers/{server_id}

Retrieves detailed information for a specified server.

The following extensions provide additional information when viewing server details:



*  Config Drive:
*  Scheduled Images:
*  Extended Status ( ``OS-EXT-STS:power_state``, ``OS-EXT-STS:vm_state``, and ``OS-EXT-STS:task_state`` ):


In the URI, specify the target server ID.



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
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{server_id}               |Uuid                     |The UUID for the server. |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Retrieve server details: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json





Response
""""""""""""""""





This table shows the body parameters for the response:

+-------------------------------+-----------------------+----------------------+
|Name                           |Type                   |Description           |
+===============================+=======================+======================+
|parameters.\ **server**        |Object                 |A container of server |
|                               |                       |details.              |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\            |Ip                     |The public IP version |
|**accessIPv4**                 |                       |4 access address.     |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\            |Ip                     |The public IP version |
|**accessIPv6**                 |                       |6 access address.     |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\            |Array                  |An array of addresses |
|**addresses**                  |                       |for public, private,  |
|                               |                       |and isolated networks |
|                               |                       |attached to the       |
|                               |                       |server.               |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\            |Array                  |The IP address of the |
|**addr**esses.\ **addr**       |                       |network.              |
+-------------------------------+-----------------------+----------------------+
|parameters.server.addresses.\  |Array                  |The version of the IP |
|**version**                    |                       |address of the        |
|                               |                       |network.              |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **id**     |Uuid                   |The ID of the server. |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **created**|Uuid                   |The time stamp        |
|                               |                       |indicating the        |
|                               |                       |creation date of the  |
|                               |                       |server.               |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **flavor** |Uuid                   |The flavor ID.        |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **image**  |Uuid                   |The image ID.         |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **hostId** |Uuid                   |The host ID. The      |
|                               |                       |compute provisioning  |
|                               |                       |algorithm has an anti-|
|                               |                       |affinity property     |
|                               |                       |that attempts to      |
|                               |                       |spread customer VMs   |
|                               |                       |across hosts. Under   |
|                               |                       |certain situations,   |
|                               |                       |VMs from the same     |
|                               |                       |customer might be     |
|                               |                       |placed on the same    |
|                               |                       |host. hostId          |
|                               |                       |represents the host   |
|                               |                       |your server runs on   |
|                               |                       |and can be used to    |
|                               |                       |determine this        |
|                               |                       |scenario if it is     |
|                               |                       |relevant to your      |
|                               |                       |application. HostId   |
|                               |                       |is unique only for an |
|                               |                       |account and is not    |
|                               |                       |globally unique.      |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **links**  |Uuid                   |An array of the self  |
|                               |                       |and bookmark links to |
|                               |                       |the server.           |
+-------------------------------+-----------------------+----------------------+
|parameters.server.links.\      |Uuid                   |The URL for the       |
|**href**                       |                       |server and the        |
|                               |                       |associated ``rel``.   |
+-------------------------------+-----------------------+----------------------+
|parameters.server.links.\      |Uuid                   |The descriptive field |
|**rel**                        |                       |for the associated    |
|                               |                       |``href``, which is    |
|                               |                       |either ``self`` or    |
|                               |                       |``bookmark``.         |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\            |String                 |Any metadata key and  |
|**metadata**                   |                       |value pairs.          |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **name**   |String                 |The server name.      |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\            |String                 |The build completion  |
|**progress**                   |                       |progress, as a        |
|                               |                       |percentage. Value     |
|                               |                       |ranges from ``0`` to  |
|                               |                       |``100``.              |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **status** |String                 |The status of the     |
|                               |                       |server. For a full    |
|                               |                       |list of possible      |
|                               |                       |status values, see.   |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\            |String                 |The tenant ID.        |
|**tenant_id**                  |                       |                      |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **updated**|String                 |The time stamp of the |
|                               |                       |last update.          |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **user_id**|String                 |The user ID.          |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **OS-      |String                 |Extended attribute:   |
|DCF:diskConfig**               |                       |The disk              |
|                               |                       |configuration value.  |
|                               |                       |Valid values are      |
|                               |                       |``AUTO`` and          |
|                               |                       |``MANUAL``.           |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **RAX-     |String                 |Extended attribute:   |
|SI:image_schedule**            |                       |The image schedule    |
|                               |                       |reference is included |
|                               |                       |only if scheduled     |
|                               |                       |images has been       |
|                               |                       |enabled for this      |
|                               |                       |server.               |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **OS-EXT-  |String                 |Extended attribute.   |
|STS**                          |                       |Shows the extended    |
|                               |                       |statuses for the      |
|                               |                       |server, including the |
|                               |                       |VM, task, and power   |
|                               |                       |states.               |
+-------------------------------+-----------------------+----------------------+
|parameters.server.\ **RAX-     |Uuid                   |Extended attribute.   |
|PUBLIC-IP-ZONE-                |                       |Enables booting the   |
|ID:publicIPZoneId**            |                       |server from a volume  |
|                               |                       |when additional       |
|                               |                       |parameters are given. |
|                               |                       |If specified, the     |
|                               |                       |volume status must be |
|                               |                       |``available``, and    |
|                               |                       |the volume            |
|                               |                       |attach_status must be |
|                               |                       |``detached``.         |
+-------------------------------+-----------------------+----------------------+
|parameters.\ **next**          |Anyuri                 |Moves to the next     |
|                               |                       |metadata item.        |
+-------------------------------+-----------------------+----------------------+
|parameters.\ **previous**      |Anyuri                 |Moves to the previous |
|                               |                       |metadata item.        |
+-------------------------------+-----------------------+----------------------+







**Example Retrieve server details: JSON response**


.. code::

       Status Code: 200 Accepted
       Content-Length: 380
       Content-Type: application/json
       Date: Thu, 04 Dec 2014 18:47:30 GMT
       Location: https://dfw.servers.api.rackspacecloud.com/v2/123456/servers/ef08aa7a-b5e4-4bb8-86df-5ac56230f841
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-b8b54344-41a9-4d6a-c29e-60f3dcab4b1f


.. code::

   {
       "server": {
           "OS-DCF:diskConfig": "AUTO",
           "OS-EXT-STS:power_state": 1,
           "OS-EXT-STS:task_state": null,
           "OS-EXT-STS:vm_state": "active",
           "accessIPv4": "198.101.241.238",
           "accessIPv6": "2001:4800:780e:0510:d87b:9cbc:ff04:513a",
           "addresses": {
               "private": [
                   {
                       "addr": "10.180.3.171",
                       "version": 4
                   }
               ],
               "public": [
                   {
                       "addr": "198.101.241.238",
                       "version": 4
                   },
                   {
                       "addr": "2001:4800:780e:0510:d87b:9cbc:ff04:513a",
                       "version": 6
                   }
               ]
           },
           "created": "2012-08-16T18:41:43Z",
           "flavor": {
               "id": "2",
               "links": [
                   {
                       "href": "https://dfw.servers.api.rackspacecloud.com/010101/flavors/2",
                       "rel": "bookmark"
                   }
               ]
           },
           "hostId": "33ccb6c82f3625748b6f2338f54d8e9df07cc583251e001355569056",
           "id": "ef08aa7a-b5e4-4bb8-86df-5ac56230f841",
           "image": {
               "id": "3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
               "links": [
                   {
                       "href": "https://dfw.servers.api.rackspacecloud.com/010101/images/3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
                       "rel": "bookmark"
                   }
               ]
           },
           "links": [
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/v2/010101/servers/ef08aa7a-b5e4-4bb8-86df-5ac56230f841",
                   "rel": "self"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/010101/servers/ef08aa7a-b5e4-4bb8-86df-5ac56230f841",
                   "rel": "bookmark"
               }
           ],
           "metadata": {
               "My Server Name": "API Test Server 2"
           },
           "name": "api-test-server 2",
           "progress": 100,
           "status": "ACTIVE",
           "tenant_id": "010101",
           "updated": "2012-08-16T18:50:38Z",
           "user_id": "170454"
       }
   }




