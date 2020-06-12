.. _post-create-bootable-volume-and-server-servers:

Create bootable volume and server
---------------------------------

.. code::

    POST /servers

This operation creates a bootable volume and boots a server in one step.

The full URL to the newly created server is returned through the ``Location``
header and is available as a ``self`` and ``bookmark`` link in the server
representation.

The progress of the server build depends on factors including location of the
requested image, network i/o, host load, and the selected flavor. You can
check the progress of the build request by issuing a call to retrieve the
details of the server. After the build completes, the server's ``status`` is
``ACTIVE``.

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
|**block_device_mapping_v2**             |             |bootable volume       |
|                                        |             |details.              |
+----------------------------------------+-------------+----------------------+
|server.block_device_mapping_v2.\        |Integer      |The index of the      |
|**boot_index**                          |             |bootable volume.      |
+----------------------------------------+-------------+----------------------+
|server.block_device_mapping_v2.\        |Integer      |The id of the         |
|**uuid**                                |             |bootable volume.      |
+----------------------------------------+-------------+----------------------+
|server.block_device_mapping_v2.\        |String       |The source type for   |
|**source_type**                         |             |the bootable volume.  |
|                                        |             |Must be ``volume``.   |
+----------------------------------------+-------------+----------------------+
|server.block_device_mapping_v2.\        |String       |The destination type  |
|**destination_type**                    |             |for the bootable      |
|                                        |             |volume.               |
+----------------------------------------+-------------+----------------------+
|server.block_device_mapping_v2.\        |Boolean      |Flag to indicate      |
|**delete_on_termination**               |             |whether the bootable  |
|                                        |             |volume should be      |
|                                        |             |deleted after server  |
|                                        |             |creation.             |
+----------------------------------------+-------------+----------------------+
|server.\ **flavorRef**                  |Uuid         |The flavor reference  |
|                                        |             |for the desired       |
|                                        |             |flavor for your       |
|                                        |             |server instance.      |
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
|                                        |             |metadata key set      |
|                                        |             |affects the value you |
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


**Example Create bootable volume and server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "server":{
           "name":"BFVServer5",
           "imageRef":"",
           "block_device_mapping_v2":[
               {
                   "boot_index":"0",
                   "uuid":"bb02b1a3-bc77-4d17-ab5b-421d89850fca",
                   "volume_size":"100",
                   "source_type":"image",
                   "destination_type":"volume",
                   "delete_on_termination":false
               }
           ],
           "flavorRef":"compute1-15",
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
     }


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
|server.\ **links**         |Uuid                    |An array of the self    |
|                           |                        |and bookmark links to   |
|                           |                        |the server.             |
+---------------------------+------------------------+------------------------+
|server.links.\ **href**    |Uuid                    |The URL for the server  |
|                           |                        |and the associated      |
|                           |                        |``rel``.                |
+---------------------------+------------------------+------------------------+
|server.links.\ **rel**     |Uuid                    |The descriptive field   |
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


**Example Create bootable volume and server: JSON response**


.. code::

   {
      "server":{
         "OS-DCF:diskConfig":"MANUAL",
         "id":"42f9607f-41c4-48e5-8206-2732aee9456b",
         "links":[
            {
               "href":"https://iad.servers.api.rackspacecloud.com/v2/596067/servers/42f9607f-41c4-48e5-8206-2732aee9456b",
               "rel":"self"
            },
            {
               "href":"https://iad.servers.api.rackspacecloud.com/596067/servers/42f9607f-41c4-48e5-8206-2732aee9456b",
               "rel":"bookmark"
            }
         ],
         "adminPass":"pass"
      }
   }




