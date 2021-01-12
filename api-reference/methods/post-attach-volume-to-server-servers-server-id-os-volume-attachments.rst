.. _post-attach-volume-to-server-servers-server-id-os-volume-attachments:

Attach volume to server
-----------------------
.. code::

    POST /servers/{server_id}/os-volume_attachments

This operation attaches a data volume to a specified server.

You can attach one or more volumes in a single request.

For information about creating volumes, see
:rax-devdocs:`Rackspace Cloud Block Storage Developer
Guide <cloud-block-storage/v1/api-reference/>`.


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

This table shows the URI parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+

This table shows the body parameters for the request:

+-------------------------------+----------------------+----------------------+
|Name                           |Type                  |Description           |
+===============================+======================+======================+
|**volumeAttachment**           |Object                |The container for the |
|                               |                      |volume attachment     |
|                               |                      |specifications.       |
+-------------------------------+----------------------+----------------------+
|volumeAttachment.\ **device**  |String                |The name of the       |
|                               |                      |device, such as       |
|                               |                      |/dev/xvdb. Specify    |
|                               |                      |``null`` for auto-    |
|                               |                      |assignment.           |
+-------------------------------+----------------------+----------------------+
|volumeAttachment.\             |Object                |The ID of the volume  |
|**volumeId**                   |                      |that you want to      |
|                               |                      |attach to the server  |
|                               |                      |instance.             |
+-------------------------------+----------------------+----------------------+


**Example Attach volume to server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "volumeAttachment":{
           "device":null,
           "volumeId":"4ab50df6-7480-45df-8604-b1ee39fe857c"
       }
   }


Response
^^^^^^^^

This table shows the body parameters for the response:

+-------------------------------+----------------------+----------------------+
|Name                           |Type                  |Description           |
+===============================+======================+======================+
|**volumeAttachment**           |Object                |The container for the |
|                               |                      |volume attachment     |
|                               |                      |specifications.       |
+-------------------------------+----------------------+----------------------+
|volumeAttachment.\ **device**  |String                |The name of the       |
|                               |                      |device, such as       |
|                               |                      |/dev/xvdb. Specify    |
|                               |                      |``null`` for auto-    |
|                               |                      |assignment.           |
+-------------------------------+----------------------+----------------------+
|volumeAttachment.\ **Id**      |String                |The ID of the volume  |
|                               |                      |that you attached to  |
|                               |                      |the server instance.  |
+-------------------------------+----------------------+----------------------+
|volumeAttachment.\             |String                |The ID of the server  |
|**serverId**                   |                      |instance to which you |
|                               |                      |attached the volume.  |
+-------------------------------+----------------------+----------------------+
|volumeAttachment.\             |String                |The ID of the volume  |
|**volumeId**                   |                      |that you attached to  |
|                               |                      |the server instance.  |
+-------------------------------+----------------------+----------------------+

**Example Attach volume to server: JSON response**


.. code::

       Status Code: 202 OK
       Content-Length: 120
       Content-Type: application/json
       Date: Mon, 19 Jan 2015 19:22:30 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-206e007a-9dfe-4ac4-b819-d64a74244506


.. code::

   {
       "volumeAttachment":{
           "device":"/dev/xvdb",
           "serverId":"76ddf257-2771-4097-aab8-b07b52110376",
           "id":"4ab50df6-7480-45df-8604-b1ee39fe857c",
           "volumeId":"4ab50df6-7480-45df-8604-b1ee39fe857c"
       }
   }




