
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _put-show-volume-attachment-details-servers-server-id-os-volume-attachments-attachment-id:

Show volume attachment details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    PUT /servers/{server_id}/os-volume_attachments/{attachment_id}

Retrieves volume details for the specified server ID and volume attachment ID

In the URI, specify the target server ID and the target attached volume ID to see details for that 				volume.



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
|{attachment_id}           |Uuid                     |The volume attachment ID.|
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Show volume attachment details: JSON request**


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
|parameters.\                   |Object                 |The container for the |
|**volumeAttachment**           |                       |volume attachment     |
|                               |                       |specifications.       |
+-------------------------------+-----------------------+----------------------+
|parameters.volumeAttachment.\  |String                 |The name of the       |
|**device**                     |                       |device, such as       |
|                               |                       |/dev/xvdb. Specify    |
|                               |                       |``null`` for auto-    |
|                               |                       |assignment.           |
+-------------------------------+-----------------------+----------------------+
|parameters.volumeAttachment.\  |String                 |The ID of the volume  |
|**Id**                         |                       |that you attached to  |
|                               |                       |the server instance.  |
+-------------------------------+-----------------------+----------------------+
|parameters.volumeAttachment.\  |String                 |The ID of the server  |
|**serverId**                   |                       |instance to which you |
|                               |                       |attached the volume.  |
+-------------------------------+-----------------------+----------------------+
|parameters.volumeAttachment.\  |String                 |The ID of the volume  |
|**volumeId**                   |                       |that you attached to  |
|                               |                       |the server instance.  |
+-------------------------------+-----------------------+----------------------+







**Example Show volume attachment details: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 32
       Content-Type: application/json
       Date: Tue, 20 Jan 2015 14:25:02 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-96b3fdf4-a6d9-42ce-91bb-2cea8eb5e14e


.. code::

   {
       "volumeAttachment":{
           "device":"/dev/xvdb",
           "serverId":"76ddf257-2771-4097-aab8-b07b52110376",
           "id":"4ab50df6-7480-45df-8604-b1ee39fe857c",
           "volumeId":"4ab50df6-7480-45df-8604-b1ee39fe857c"
       }
   }




