
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-list-servers-with-details-servers-detail:

List servers with details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /servers/detail

Retrieves a detailed list of all servers in the tenant's account.

Servers contain a status attribute that indicates the current server state. You can filter on the server 				status when you complete a list servers request. The server status is returned in the response body. For a 				full list of possible server status values, see.

The following extensions provide additional information when viewing server details:



*  Config Drive:
*  Scheduled Images:
*  Extended Status ( ``OS-EXT-STS:power_state``, ``OS-EXT-STS:vm_state``, and ``OS-EXT-STS:task_state`` ):
*  Block Device Mapping:


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




**Example List servers with details: JSON request**


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
|servers                   |Array                    |An array of servers.     |
+--------------------------+-------------------------+-------------------------+
|accessIPv4                |Ip                       |The public IP version 4  |
|                          |                         |access address.          |
+--------------------------+-------------------------+-------------------------+
|accessIPv6                |Ip                       |The public IP version 6  |
|                          |                         |access address.          |
+--------------------------+-------------------------+-------------------------+
|addresses                 |Array                    |An array of addresses    |
|                          |                         |for public, private, and |
|                          |                         |isolated networks        |
|                          |                         |attached to the server.  |
+--------------------------+-------------------------+-------------------------+
|addr                      |Array                    |The IP address of the    |
|                          |                         |network.                 |
+--------------------------+-------------------------+-------------------------+
|version                   |Array                    |The version of the IP    |
|                          |                         |address of the network.  |
+--------------------------+-------------------------+-------------------------+
|id                        |Uuid                     |The ID of the server.    |
+--------------------------+-------------------------+-------------------------+
|created                   |Uuid                     |The time stamp           |
|                          |                         |indicating the creation  |
|                          |                         |date of the server.      |
+--------------------------+-------------------------+-------------------------+
|flavor                    |Uuid                     |The flavor ID..          |
+--------------------------+-------------------------+-------------------------+
|image                     |Uuid                     |The image ID..           |
+--------------------------+-------------------------+-------------------------+
|hostId                    |Uuid                     |The host ID. The compute |
|                          |                         |provisioning algorithm   |
|                          |                         |has an anti-affinity     |
|                          |                         |property that attempts   |
|                          |                         |to spread customer VMs   |
|                          |                         |across hosts. Under      |
|                          |                         |certain situations, VMs  |
|                          |                         |from the same customer   |
|                          |                         |might be placed on the   |
|                          |                         |same host. hostId        |
|                          |                         |represents the host your |
|                          |                         |server runs on and can   |
|                          |                         |be used to determine     |
|                          |                         |this scenario if it is   |
|                          |                         |relevant to your         |
|                          |                         |application. HostId is   |
|                          |                         |unique only for an       |
|                          |                         |account and is not       |
|                          |                         |globally unique.         |
+--------------------------+-------------------------+-------------------------+
|links                     |Uuid                     |An array of the self and |
|                          |                         |bookmark links to the    |
|                          |                         |server.                  |
+--------------------------+-------------------------+-------------------------+
|href                      |Uuid                     |The URL for the server   |
|                          |                         |and the associated       |
|                          |                         |``rel``.                 |
+--------------------------+-------------------------+-------------------------+
|rel                       |Uuid                     |The descriptive field    |
|                          |                         |for the associated       |
|                          |                         |``href``, which is       |
|                          |                         |either ``self`` or       |
|                          |                         |``bookmark``.            |
+--------------------------+-------------------------+-------------------------+
|metadata                  |String                   |Any metadata key and     |
|                          |                         |value pairs.             |
+--------------------------+-------------------------+-------------------------+
|name                      |String                   |The server name.         |
+--------------------------+-------------------------+-------------------------+
|progress                  |String                   |The build completion     |
|                          |                         |progress, as a           |
|                          |                         |percentage. Value ranges |
|                          |                         |from 0 to 100.           |
+--------------------------+-------------------------+-------------------------+
|status                    |String                   |The status of the        |
|                          |                         |server. For a full list  |
|                          |                         |of possible status       |
|                          |                         |values, see.             |
+--------------------------+-------------------------+-------------------------+
|tenant_id                 |String                   |The tenant ID.           |
+--------------------------+-------------------------+-------------------------+
|updated                   |String                   |The time stamp of the    |
|                          |                         |last update.             |
+--------------------------+-------------------------+-------------------------+
|user_id                   |String                   |The user ID.             |
+--------------------------+-------------------------+-------------------------+
|OS-DCF:diskConfig         |String                   |Extended attribute: The  |
|                          |                         |disk configuration       |
|                          |                         |value.. Valid values are |
|                          |                         |``AUTO`` and ``MANUAL``. |
+--------------------------+-------------------------+-------------------------+
|RAX-SI:image_schedule     |String                   |Extended attribute: The  |
|                          |                         |image schedule reference |
|                          |                         |is included only if      |
|                          |                         |scheduled images has     |
|                          |                         |been enabled for this    |
|                          |                         |server..                 |
+--------------------------+-------------------------+-------------------------+
|OS-EXT-STS                |String                   |Extended attribute.      |
|                          |                         |Shows the extended       |
|                          |                         |statuses for the server, |
|                          |                         |including the VM, task,  |
|                          |                         |and power states..       |
+--------------------------+-------------------------+-------------------------+
|RAX-PUBLIC-IP-ZONE-       |Uuid                     |Extended attribute.      |
|ID:publicIPZoneId         |                         |Enables booting the      |
|                          |                         |server from a volume     |
|                          |                         |when additional          |
|                          |                         |parameters are given. If |
|                          |                         |specified, the volume    |
|                          |                         |status must be           |
|                          |                         |``available``, and the   |
|                          |                         |volume attach_status     |
|                          |                         |must be ``detached``.    |
+--------------------------+-------------------------+-------------------------+
|next                      |Anyuri                   |Moves to the next        |
|                          |                         |metadata item.           |
+--------------------------+-------------------------+-------------------------+
|previous                  |Anyuri                   |Moves to the previous    |
|                          |                         |metadata item.           |
+--------------------------+-------------------------+-------------------------+







**Example List servers with details: JSON response**


The following example show only one server in the list for brevity.

.. code::

       Status Code: 200 OK
       Content-Length: 4543
       Content-Type: application/json
       Date: Wed, 03 Dec 2014 17:13:30 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-7b7ffed2-9b1f-46a8-a478-315518d35387


.. code::

   {
     "servers": [
       {
         "status": "ACTIVE",
         "updated": "2014-05-28T18:49:33Z",
         "hostId": "621cca5902d18b025468ae8e6bdcbbd5649a1ffe577716f267be4a93",
         "addresses": {
           "public": [
             {
               "version": 4,
               "addr": "198.61.212.87"
             },
             {
               "version": 6,
               "addr": "2001:4800:780e:0510:7e32:e3ee:ff04:ddc8"
             }
           ],
           "private": [
             {
               "version": 4,
               "addr": "10.180.19.16"
             }
           ],
           "SecureNet": [
             {
               "version": 4,
               "addr": "192.168.3.2"
             }
           ]
         },
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
         "key_name": null,
         "image": {
           "id": "f19067a2-7233-4666-b0f2-f420a4776ff0",
           "links": [
             {
               "href": "https://dfw.servers.api.rackspacecloud.com/123456/images/f19067a2-7233-4666-b0f2-f420a4776ff0",
               "rel": "bookmark"
             }
           ]
         },
         "RAX-PUBLIC-IP-ZONE-ID:publicIPZoneId": "d12f4c3ef88ff2ca471f6b1a57d108c15db4a3478af762da6ae022b7",
         "OS-EXT-STS:task_state": null,
         "OS-EXT-STS:vm_state": "active",
         "RAX-SI:image_schedule": {
             "retention": 3
         }, 
         "flavor": {
           "id": "2",
           "links": [
             {
               "href": "https://dfw.servers.api.rackspacecloud.com/123456/flavors/2",
               "rel": "bookmark"
             }
           ]
         },
         "id": "5bccf43e-35fa-4d65-9390-2b2d6b23ec89",
         "user_id": "346289",
         "name": "DB2",
         "created": "2013-07-23T15:44:56Z",
         "tenant_id": "123456",
         "OS-DCF:diskConfig": "AUTO",
         "accessIPv4": "198.61.212.87",
         "accessIPv6": "2001:4800:780e:510:7e32:e3ee:ff04:ddc8",
         "progress": 100,
         "OS-EXT-STS:power_state": 1,
         "config_drive": "",
         "metadata": {}
       }
     ]
   }




