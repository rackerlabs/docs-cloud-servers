
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _put-update-server-servers-server-id:

Update server
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    PUT /servers/{server_id}

Updates one or more editable attributes for a specified server.

The attributes that can be edited are: name, accessIPv4, and accessIPv6. You can update any or all of the 				attributes in a single request.

.. note::
   If you try to update a server by using the server bookmark link, the response code is 300, unless you 					use the Accept: application/json;version=1.1 header with the request.
   
   

In the URI, specify the target server ID.

In the request body, specify the element ``server``, followed by the attribute, for example ``name``, with the new value for that attribute. You can include one or more attributes in 				the server element.



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





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|parameters.\ **server**   |Object *(Required)*      |A container for one or   |
|                          |                         |more server details to   |
|                          |                         |be updated.              |
+--------------------------+-------------------------+-------------------------+
|parameters.server.\       |String *(Optional)*      |The server name.         |
|**name**                  |                         |                         |
+--------------------------+-------------------------+-------------------------+
|parameters.server.\       |Ip *(Optional)*          |The public IP version 4  |
|**accessIPv4**            |                         |access address.          |
+--------------------------+-------------------------+-------------------------+
|parameters.server.\       |Ip *(Optional)*          |The public IP version 6  |
|**accessIPv6**            |                         |access address.          |
+--------------------------+-------------------------+-------------------------+





**Example Update server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "server" :{
          "name" : "new-test-server-1"
       }
   }





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







**Example Update server: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 1250
       Content-Type: application/json
       Date: Thu, 04 Dec 2014 19:41:58 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-8c905dfe-2c9a-42d9-8e53-4478e2813c75


.. code::

   {
     "server": {
       "status": "ACTIVE",
       "updated": "2014-12-04T19:41:58Z",
       "hostId": "d535dcad0d51c97d20910a3c2a8264f0be8b847b8982e305bee27389",
       "addresses": {
         "public": [
           {
             "version": 6,
             "addr": "2001:4800:7812:514:be76:4eff:fe05:aaed"
           },
           {
             "version": 4,
             "addr": "166.78.149.149"
           }
         ],
         "private": [
           {
             "version": 4,
             "addr": "10.182.16.182"
           }
         ]
       },
       "links": [
         {
           "href": "https://dfw.servers.api.rackspacecloud.com/v2/123456/servers/4b963871-f591-4b7d-b05f-7c0286e3c50f",
           "rel": "self"
         },
         {
           "href": "https://dfw.servers.api.rackspacecloud.com/123456/servers/4b963871-f591-4b7d-b05f-7c0286e3c50f",
           "rel": "bookmark"
         }
       ],
       "image": {
         "id": "3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/123456/images/3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
             "rel": "bookmark"
           }
         ]
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
       "id": "4b963871-f591-4b7d-b05f-7c0286e3c50f",
       "user_id": "346762",
       "name": "new-testserver-1",
       "created": "2014-12-04T18:47:30Z",
       "tenant_id": "123456",
       "OS-DCF:diskConfig": "AUTO",
       "accessIPv4": "166.78.149.149",
       "accessIPv6": "2001:4800:7812:514:be76:4eff:fe05:aaed",
       "progress": 100,
       "metadata": {
         "My Server Name": "API Test Server 1"
       }
     }
   }




