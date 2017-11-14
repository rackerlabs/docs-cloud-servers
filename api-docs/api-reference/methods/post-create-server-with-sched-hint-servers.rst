.. _post-create-server-with-sched-hint-servers:

Create server with scheduler hints
----------------------------------

.. code::

    POST /servers

This operation creates a server using a scheduler hint.

A scheduler hint allows a cloud server to be built near to, or far from, an
existing server within a specific zone. Use either the ``public-zone-ip:near``
or the ``public-zone-ip:far`` parameter and be sure to use the server`s ``ID``
and not the server's ``zone`` when making the request.

If a build request with a hint can not be satisfied then the build
will not succeed, and the server, which will have a  status of ``ERROR`` and a
task state of ``scheduling``, must be manually deleted.

A zone is a logical container for servers. The Public IP Zone is the zone in
which a Public IP can be shared between two or more servers.

.. note:
   A Public IP Zone will contain servers that are all made up of the same
   flavor class. For example a General Purpose - 1 server will never share a
   Public IP Zone with a Memory - 1 server.

The ``public-zone-ip:near`` and ``public-zone-ip:far`` parameters allow you
specify up to three server IP addresses, but we recommend you use just one IP
address to reduce chance of failure.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|202                      |Success                  |Request accepted.        |
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

This table shows the body parameters for the request:

+----------------------------------------+-------------+----------------------+
|Name                                    |Type         |Description           |
+========================================+=============+======================+
|server.\ **name**                       |String       |The server name.      |
|                                        |             |                      |
+----------------------------------------+-------------+----------------------+
|server.\ **imageRef**                   |Uuid         |The image reference   |
|                                        |             |for the desired image |
|                                        |             |for your server       |
|                                        |             |instance.             |
+----------------------------------------+-------------+----------------------+
|server.\                                |Object       |The container of      |
|**block_device_mapping_v2**             |*(Optional)* |bootable volume       |
|                                        |             |details.              |
+----------------------------------------+-------------+----------------------+
|server.\ block_device_mapping_v2.\      |Integer      |The index of the      |
|**boot_index**                          |*(Optional)* |bootable volume.      |
+----------------------------------------+-------------+----------------------+
|server.\ block_device_mapping_v2.\      |Integer      |The id of the         |
|**uuid**                                |*(Optional)* |bootable volume.      |
+----------------------------------------+-------------+----------------------+
|server.\ block_device_mapping_v2.\      |String       |The source type for   |
|**source_type**                         |*(Optional)* |the bootable volume.  |
+----------------------------------------+-------------+----------------------+
|server.\ block_device_mapping_v2.\      |String       |The destination type  |
|**destination_type**                    |*(Optional)* |for the bootable      |
|                                        |             |volume.               |
+----------------------------------------+-------------+----------------------+
|server.\ block_device_mapping_v2.\      |Boolean      |Flag to indicate      |
|**delete_on_termination**               |*(Optional)* |whether the bootable  |
|                                        |             |volume should be      |
|                                        |             |deleted after server  |
|                                        |             |creation.             |
+----------------------------------------+-------------+----------------------+
|server.\ **flavorRef**                  |Uuid         |The flavor reference  |
|                                        |*(Required)* |for the desired       |
|                                        |             |flavor for your       |
|                                        |             |server instance.      |
+----------------------------------------+-------------+----------------------+
|server.\ **os:scheduler_hints**         |Uuid         |The container for     |
|                                        |*(Optional)* |a scheduler hint.     |
+----------------------------------------+-------------+----------------------+
|server.\ os:scheduler_hints\            |Uuid         |An array of server IDs|
|**public_ip_zone:near**                 |*(Optional)* |that new server will  |
|                                        |             |built near. One to    |
|                                        |             |three server IDs may  |
|                                        |             |listed.               |
+----------------------------------------+-------------+----------------------+
|server.\ os:scheduler_hints\            |Uuid         |Alternative to        |
|**public_ip_zone:far**                  |*(Optional)* |public_ip_zone:near   |
|                                        |             |that specifies the new|
|                                        |             |server should be built|
|                                        |             |far from the specified|
|                                        |             |server(s).            |
+----------------------------------------+-------------+----------------------+
|server.\ **config_drive**               |String       |Enables metadata      |
|                                        |*(Optional)* |injection in a server |
|                                        |             |through a             |
|                                        |             |configuration drive.  |
|                                        |             |To enable a           |
|                                        |             |configuration drive,  |
|                                        |             |specify ``true``.     |
|                                        |             |Otherwise, specify    |
|                                        |             |``false``.            |
+----------------------------------------+-------------+----------------------+
|server.\ **key_name**                   |String       |The name of the key   |
|                                        |*(Optional)* |pair used to          |
|                                        |             |authenticate by using |
|                                        |             |key-based             |
|                                        |             |authentication        |
|                                        |             |instead of password-  |
|                                        |             |based authentication. |
+----------------------------------------+-------------+----------------------+
|server.\ **OS-DCF:diskConfig**          |String       |The disk              |
|                                        |*(Optional)* |configuration value.  |
|                                        |             |The image             |
|                                        |             |auto_disk_config      |
|                                        |             |metadata key set will |
|                                        |             |affect the value you  |
|                                        |             |can choose to set the |
|                                        |             |server ``OS-          |
|                                        |             |DCF:diskConfig``. If  |
|                                        |             |an image has          |
|                                        |             |``auto_disk_config``  |
|                                        |             |value of              |
|                                        |             |``disabled``, you     |
|                                        |             |cannot create a       |
|                                        |             |server from that      |
|                                        |             |image when specifying |
|                                        |             |``OS-DCF:diskConfig`` |
|                                        |             |value of ``AUTO``.    |
|                                        |             |Valid values are:     |
|                                        |             |AUTO:The server is    |
|                                        |             |built with a single   |
|                                        |             |partition which is    |
|                                        |             |the size of the       |
|                                        |             |target flavor disk.   |
|                                        |             |The file system is    |
|                                        |             |automatically         |
|                                        |             |adjusted to fit the   |
|                                        |             |entire partition.     |
|                                        |             |This keeps things     |
|                                        |             |simple and automated. |
|                                        |             |AUTO is valid only    |
|                                        |             |for images and        |
|                                        |             |servers with a single |
|                                        |             |partition that use    |
|                                        |             |the EXT3 file system. |
|                                        |             |This is the default   |
|                                        |             |setting for           |
|                                        |             |applicable Rackspace  |
|                                        |             |base images.          |
|                                        |             |MANUAL:The server is  |
|                                        |             |built using the       |
|                                        |             |partition scheme and  |
|                                        |             |file system of the    |
|                                        |             |source image. If the  |
|                                        |             |target flavor disk is |
|                                        |             |larger, the remaining |
|                                        |             |disk space is left    |
|                                        |             |unpartitioned. This   |
|                                        |             |enables images to     |
|                                        |             |have non-EXT3 file    |
|                                        |             |systems, multiple     |
|                                        |             |partitions, and so    |
|                                        |             |on, and it enables    |
|                                        |             |you to manage the     |
|                                        |             |disk configuration.   |
+----------------------------------------+-------------+----------------------+
|server.\ **metadata**                   |String       |Metadata key and      |
|                                        |*(Optional)* |value pairs. The      |
|                                        |             |maximum size of each  |
|                                        |             |metadata key and      |
|                                        |             |value is 255 bytes    |
|                                        |             |each.                 |
+----------------------------------------+-------------+----------------------+
|server.\ **personality**                |Array        |The array of          |
|                                        |*(Optional)* |personality files for |
|                                        |             |the server.           |
+----------------------------------------+-------------+----------------------+
|server.\ **user_data**                  |String       |Data used with        |
|                                        |*(Optional)* |config_drive for      |
|                                        |             |configuring a server. |
+----------------------------------------+-------------+----------------------+
|server.personality.\ **path**           |String       |The path of the       |
|                                        |             |personality file.     |
+----------------------------------------+-------------+----------------------+
|server.personality.\ **contents**       |String       |The contents of the   |
|                                        |             |personality file.     |
+----------------------------------------+-------------+----------------------+
|server.\ **networks**                   |Array        |The array of networks |
|                                        |             |attached to the       |
|                                        |             |server. By default,   |
|                                        |             |the server instance   |
|                                        |             |is provisioned with   |
|                                        |             |all isolated networks |
|                                        |             |for the tenant. You   |
|                                        |             |can specify multiple  |
|                                        |             |NICs on the server.   |
|                                        |             |Optionally, you can   |
|                                        |             |create one or more    |
|                                        |             |NICs on the server.   |
|                                        |             |To provision the      |
|                                        |             |server instance with  |
|                                        |             |a NIC for a ``Nova-   |
|                                        |             |network`` network,    |
|                                        |             |specify the UUID in   |
|                                        |             |the ``uuid``          |
|                                        |             |attribute in a        |
|                                        |             |``networks`` object.  |
|                                        |             |To provision the      |
|                                        |             |server instance with  |
|                                        |             |a NIC for a           |
|                                        |             |``Neutron`` network,  |
|                                        |             |specify the UUID in   |
|                                        |             |the ``port``          |
|                                        |             |attribute in a        |
|                                        |             |``networks`` object.  |
+----------------------------------------+-------------+----------------------+
|server.networks.\ **uuid**              |Uuid         |The UUID of the       |
|                                        |*(Optional)* |``Nova-network``      |
|                                        |             |network attached to   |
|                                        |             |the server.           |
+----------------------------------------+-------------+----------------------+
|server.networks.\ **port**              |Uuid         |The UUID of the       |
|                                        |*(Optional)* |``Neutron`` port      |
|                                        |             |attached to the       |
|                                        |             |server.               |
+----------------------------------------+-------------+----------------------+


**Example Create server with scheduler hint: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


..  code::

	{

	   "os:scheduler_hints":{
		  "public_ip_zone:near":["f841bab4-8c12-4223-a60f-76b224e053cf", "additional uuid", "additional uuid"]
	   },
	   "server":{
		  "name":"TestIpZone2",
		  "imageRef":"055143e8-2da9-439a-a52d-8063f845dec6",
		  "flavorRef":"general1-1",
		  "max_count":1,
		  "min_count":1,
		  "networks":[
			 {
				"uuid":"00000000-0000-0000-0000-000000000000"
			 },
			 {
				"uuid":"11111111-1111-1111-1111-111111111111"
			 }
		  ]
	   }
	}'


Response
^^^^^^^^

This table shows the body parameters for the response:

+---------------------------+------------------------+------------------------+
|Name                       |Type                    |Description             |
+===========================+========================+========================+
|**server**                 |Object                  |The container for       |
|                           |                        |server data.            |
+---------------------------+------------------------+------------------------+
|server.\ **id**            |Uuid                    |The ID of the server.   |
+---------------------------+------------------------+------------------------+
|server.\ **links**         |Array                   |An array of the self    |
|                           |                        |and bookmark links to   |
|                           |                        |the server.             |
+---------------------------+------------------------+------------------------+
|server.links.\ **href**    |String                  |The URL for the server  |
|                           |                        |and the associated      |
|                           |                        |``rel``.                |
+---------------------------+------------------------+------------------------+
|server.links.\ **rel**     |String                  |The descriptive field   |
|                           |                        |for the associated      |
|                           |                        |``href``, which is      |
|                           |                        |either ``self`` or      |
|                           |                        |``bookmark``.           |
+---------------------------+------------------------+------------------------+
|server.\ **adminPass**     |String                  |The password assigned   |
|                           |                        |to provide login access |
|                           |                        |to the server.          |
+---------------------------+------------------------+------------------------+
|server.\ **OS-             |String                  |The disk configuration  |
|DCF:diskConfig**           |                        |value. Valid values are |
|                           |                        |``AUTO`` and ``MANUAL``.|
+---------------------------+------------------------+------------------------+


**Example Create server with scheduler hint: JSON response**


.. code::

       Status Code: 202 Accepted
       Content-Length: 380
       Content-Type: application/json
       Date: Fri, 30 Jan 2015 18:38:52 GMT
       Location: https://dfw.servers.api.rackspacecloud.com/v2/820712/servers/b7509240-9ad2-4303-8614-a11a33aeb6f3
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-186f2212-f4b7-4d0a-bbbb-92bc19797a1d


.. code::

   {
     "server": {
       "OS-DCF:diskConfig": "AUTO",
       "id": "a4209240-5ed2-4793-8614-a11a33aed22a",
       "links": [
         {
           "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/servers/b7509240-9ad2-4303-8614-a11a33aeb6f3",
           "rel": "self"
         },
         {
           "href": "https://dfw.servers.api.rackspacecloud.com/820712/servers/b7509240-9ad2-4303-8614-a11a33aeb6f3",
           "rel": "bookmark"
         }
       ],
       "adminPass": "sYr9cptCwsLx"
     }
   }




