.. _get-list-servers-server-id-os-volume-attachments:

List server volumes
-------------------

.. code::

    GET /servers/{server_id}/os-volume_attachments

This operation retrieves list of all attached volumes for a specified server.

In the URI, specify the target server ID.

For information about creating volumes, see
:rax-devdocs:`Rackspace Cloud Block Storage Developer
Guide <cloud-block-storage/v1/api-reference/>`.


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


This table shows the URI parameters for the request:

+-------------------------+-------------------------+-------------------------+
|Name                     |Type                     |Description              |
+=========================+=========================+=========================+
|{server_id}              |Uuid                     |The UUID for the server. |
+-------------------------+-------------------------+-------------------------+

This operation does not accept a request body.

**Example List server volumes: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------------+---------------------+----------------------+
|Name                            |Type                 |Description           |
+================================+=====================+======================+
|volumeAttachment                |Array                |The array of attached |
|                                |                     |volumes.              |
+--------------------------------+---------------------+----------------------+
|volumeAttachments.\ **device**  |String               |The name of the       |
|                                |                     |device, such as       |
|                                |                     |/dev/xvdb.            |
+--------------------------------+---------------------+----------------------+
|volumeAttachments.\ **Id**      |String               |The ID of the volume  |
|                                |                     |attached to the       |
|                                |                     |server instance.      |
+--------------------------------+---------------------+----------------------+
|volumeAttachments.\ **serverId**|String               |The ID of the server  |
|                                |                     |instance to which the |
|                                |                     |volume is attached.   |
+--------------------------------+---------------------+----------------------+
|volumeAttachments.\ **volumeId**|String               |The ID of the volume  |
|                                |                     |attached to the       |
|                                |                     |server instance.      |
+--------------------------------+---------------------+----------------------+


**Example List server volumes: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 120
       Content-Type: application/json
       Date: Mon, 19 Jan 2015 19:22:30 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-206e007a-9dfe-4ac4-b819-d64a74244506


.. code::

   {
       "volumeAttachments":[
           {
               "device":"/dev/xvdb",
               "serverId":"76ddf257-2771-4097-aab8-b07b52110376",
               "id":"4ab50df6-7480-45df-8604-b1ee39fe857c",
               "volumeId":"4ab50df6-7480-45df-8604-b1ee39fe857c"
           }
       ]
   }




