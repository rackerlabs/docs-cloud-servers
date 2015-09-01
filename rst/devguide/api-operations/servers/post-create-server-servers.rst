
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Create server
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /servers

Provisions a server asynchronously.

The full URL to the newly created server is returned through the ``Location`` header and is 				available as a ``self`` and ``bookmark`` link in the server representation.

The progress of the server build depends on factors including location of the requested image, network i/o, 				host load, and the selected flavor. You can check the progress of the build request by issuing a call to 				retrieve the details of the server. Once the build is complete, the server's ``status`` is ``ACTIVE``.

For OnMetal server builds, even after the ``status`` is ACTIVE, wait a few additional 				moments for the network configuration to complete. Once the new OnMetal server pings successfully, you can 				begin to use it.

OnMetal servers must be created using an ssh key pair. Thus you should ignore the administrator 					password returned by a Create Server operation because it does not allow access to the OnMetal server.

The following extensions allow you to use other options when creating a new server:



*  Config drive
*  Boot from volume
*  Networks for nova and for neutron
*  Key pairs




This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Success                  |Request succeeded.       |
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
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""






This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|name                      |String *(Required)*      |The server name.         |
+--------------------------+-------------------------+-------------------------+
|imageRef                  |Uuid *(Required)*        |The image reference for  |
|                          |                         |the desired image for    |
|                          |                         |your server instance.    |
+--------------------------+-------------------------+-------------------------+
|block_device_mapping_v2   |Object *(Optional)*      |The container of         |
|                          |                         |bootable volume details. |
+--------------------------+-------------------------+-------------------------+
|boot_index                |Integer *(Optional)*     |The index of the         |
|                          |                         |bootable volume.         |
+--------------------------+-------------------------+-------------------------+
|uuid                      |Integer *(Optional)*     |The id of the bootable   |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|source_type               |String *(Optional)*      |The source type for the  |
|                          |                         |bootable volume.         |
+--------------------------+-------------------------+-------------------------+
|destination_type          |String *(Optional)*      |The destination type for |
|                          |                         |the bootable volume.     |
+--------------------------+-------------------------+-------------------------+
|delete_on_termination     |Boolean *(Optional)*     |Flag to indicate whether |
|                          |                         |the bootable volume      |
|                          |                         |should be deleted after  |
|                          |                         |server creation.         |
+--------------------------+-------------------------+-------------------------+
|flavorRef                 |Uuid *(Required)*        |The flavor reference for |
|                          |                         |the desired flavor for   |
|                          |                         |your server instance.    |
+--------------------------+-------------------------+-------------------------+
|config_drive              |String *(Optional)*      |Enables metadata         |
|                          |                         |injection in a server    |
|                          |                         |through a configuration  |
|                          |                         |drive. To enable a       |
|                          |                         |configuration drive,     |
|                          |                         |specify ``true``.        |
|                          |                         |Otherwise, specify       |
|                          |                         |``false``.               |
+--------------------------+-------------------------+-------------------------+
|key_name                  |String *(Optional)*      |The name of the key pair |
|                          |                         |used to authenticate by  |
|                          |                         |using key-based          |
|                          |                         |authentication instead   |
|                          |                         |of password-based        |
|                          |                         |authentication.          |
+--------------------------+-------------------------+-------------------------+
|OS-DCF:diskConfig         |String *(Optional)*      |The disk configuration   |
|                          |                         |value. The image         |
|                          |                         |auto_disk_config         |
|                          |                         |metadata key set will    |
|                          |                         |affect the value you can |
|                          |                         |choose to set the server |
|                          |                         |``OS-DCF:diskConfig``.   |
|                          |                         |If an image has          |
|                          |                         |``auto_disk_config``     |
|                          |                         |value of ``disabled``,   |
|                          |                         |you cannot create a      |
|                          |                         |server from that image   |
|                          |                         |when specifying ``OS-    |
|                          |                         |DCF:diskConfig`` value   |
|                          |                         |of ``AUTO``. Valid       |
|                          |                         |values are: AUTO:The     |
|                          |                         |server is built with a   |
|                          |                         |single partition which   |
|                          |                         |is the size of the       |
|                          |                         |target flavor disk. The  |
|                          |                         |file system is           |
|                          |                         |automatically adjusted   |
|                          |                         |to fit the entire        |
|                          |                         |partition. This keeps    |
|                          |                         |things simple and        |
|                          |                         |automated. AUTO is valid |
|                          |                         |only for images and      |
|                          |                         |servers with a single    |
|                          |                         |partition that use the   |
|                          |                         |EXT3 file system. This   |
|                          |                         |is the default setting   |
|                          |                         |for applicable Rackspace |
|                          |                         |base images. MANUAL:The  |
|                          |                         |server is built using    |
|                          |                         |the partition scheme and |
|                          |                         |file system of the       |
|                          |                         |source image. If the     |
|                          |                         |target flavor disk is    |
|                          |                         |larger, the remaining    |
|                          |                         |disk space is left       |
|                          |                         |unpartitioned. This      |
|                          |                         |enables images to have   |
|                          |                         |non-EXT3 file systems,   |
|                          |                         |multiple partitions, and |
|                          |                         |so on, and it enables    |
|                          |                         |you to manage the disk   |
|                          |                         |configuration.           |
+--------------------------+-------------------------+-------------------------+
|metadata                  |String *(Optional)*      |Metadata key and value   |
|                          |                         |pairs. The maximum size  |
|                          |                         |of each metadata key and |
|                          |                         |value is 255 bytes each. |
+--------------------------+-------------------------+-------------------------+
|personality               |Array *(Optional)*       |The array of personality |
|                          |                         |files for the server.    |
+--------------------------+-------------------------+-------------------------+
|user_data                 |String *(Optional)*      |Data used with           |
|                          |                         |config_drive for         |
|                          |                         |configuring a server.    |
+--------------------------+-------------------------+-------------------------+
|path                      |String *(Required)*      |The path of the          |
|                          |                         |personality file.        |
+--------------------------+-------------------------+-------------------------+
|contents                  |String *(Required)*      |The contents od the      |
|                          |                         |personality file.        |
+--------------------------+-------------------------+-------------------------+
|networks                  |Array *(Required)*       |The array of networks    |
|                          |                         |attached to the server.  |
|                          |                         |By default, the server   |
|                          |                         |instance is provisioned  |
|                          |                         |with all isolated        |
|                          |                         |networks for the tenant. |
|                          |                         |You can specify multiple |
|                          |                         |NICs on the server.      |
|                          |                         |Optionally, you can      |
|                          |                         |create one or more NICs  |
|                          |                         |on the server. To        |
|                          |                         |provision the server     |
|                          |                         |instance with a NIC for  |
|                          |                         |a ``Nova-network``       |
|                          |                         |network, specify the     |
|                          |                         |UUID in the ``uuid``     |
|                          |                         |attribute in a           |
|                          |                         |``networks`` object. To  |
|                          |                         |provision the server     |
|                          |                         |instance with a NIC for  |
|                          |                         |a ``Neutron`` network,   |
|                          |                         |specify the UUID in the  |
|                          |                         |``port`` attribute in a  |
|                          |                         |``networks`` object.     |
+--------------------------+-------------------------+-------------------------+
|uuid                      |Uuid *(Optional)*        |The UUID of the ``Nova-  |
|                          |                         |network`` network        |
|                          |                         |attached to the server.  |
+--------------------------+-------------------------+-------------------------+
|port                      |Uuid *(Optional)*        |The UUID of the          |
|                          |                         |``Neutron`` port         |
|                          |                         |attached to the server.  |
+--------------------------+-------------------------+-------------------------+





**Example Create server: JSON request**


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
|server                    |Object                   |The container for server |
|                          |                         |data.                    |
+--------------------------+-------------------------+-------------------------+
|id                        |Uuid                     |The ID of the server.    |
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
|adminPass                 |String                   |The password assigned to |
|                          |                         |provide login access to  |
|                          |                         |the server.              |
+--------------------------+-------------------------+-------------------------+
|OS-DCF:diskConfig         |String                   |The disk configuration   |
|                          |                         |value. Valid values are  |
|                          |                         |``AUTO`` and ``MANUAL``. |
+--------------------------+-------------------------+-------------------------+





**Example Create server: JSON response**


.. code::

        Status Code: 202 Accepted
        Content-Length: 380
        Content-Type: application/json
        Date: Thu, 04 Dec 2014 18:47:30 GMT
        Location: https://dfw.servers.api.rackspacecloud.com/v2/820712/servers/4b963871-f591-4b7d-b05f-7c0286e3c50f
        Server: Jetty(8.0.y.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/2.12)
        x-compute-request-id: req-b8b54344-41a9-4d6a-a92f-60f3dcab4b1f


