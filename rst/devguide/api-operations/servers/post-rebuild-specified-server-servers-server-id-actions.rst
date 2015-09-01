
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Rebuild specified server
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /servers/{server_id}/actions

Rebuild the specified server.

The rebuild operation removes all data on the server and replaces it with the specified image. The serverID 				and all IP addresses remain the same. If you specify name, metadata, accessIPv4, or accessIPv6 in the rebuild 				request, new values replace existing values. Otherwise, these values do not change. You can inject data into 				the file system during the rebuild.

.. note::
   This operation is not available for OnMetal servers.
   
   

Specify the target server ID in the URI.

In the request body, specify the rebuild action followed by various attributes, listed in the following 				parameters section.



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
|rebuild                   |Object *(Required)*      |Specification of the     |
|                          |                         |rebuild action for the   |
|                          |                         |specified server.        |
+--------------------------+-------------------------+-------------------------+
|name                      |Object *(Optional)*      |The new name for the     |
|                          |                         |server.                  |
+--------------------------+-------------------------+-------------------------+
|imageRef                  |Object *(Required)*      |The image ID.            |
+--------------------------+-------------------------+-------------------------+
|accessIPv4                |Object *(Optional)*      |The IP version 4 address.|
+--------------------------+-------------------------+-------------------------+
|accessIPv6                |Object *(Optional)*      |The IP version 6 address.|
+--------------------------+-------------------------+-------------------------+
|adminPass                 |String *(Optional)*      |The password assigned to |
|                          |                         |provide login access to  |
|                          |                         |the server.              |
+--------------------------+-------------------------+-------------------------+
|metadata                  |String *(Optional)*      |A metadata key and value |
|                          |                         |pair.                    |
+--------------------------+-------------------------+-------------------------+
|personality               |String *(Optional)*      |The file path and file   |
|                          |                         |contents.                |
+--------------------------+-------------------------+-------------------------+
|OS-DCF:diskConfig         |String *(Optional)*      |The disk configuration   |
|                          |                         |value. Valid values are: |
|                          |                         |AUTO:The server is built |
|                          |                         |with a single partition  |
|                          |                         |which is the size of the |
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





**Example Rebuild specified server: JSON request**


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





**Example Rebuild specified server: JSON response**


.. code::

        Status Code: 202 OK
        Content-Length: 1250
        Content-Type: application/json
        Date: Thu, 04 Dec 2014 19:41:58 GMT
        Server: Jetty(8.0.y.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/2.12)
        x-compute-request-id: req-8c905dfe-2c9a-42d9-8e53-4478e2813c75


