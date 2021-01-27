.. _get-show-server-metadata-item-details-servers-server-id-metadata-key:

Show server metadata item details
---------------------------------

.. code::

    GET /servers/{server_id}/metadata/{key}

Retrieves a metadata item by key for a specified server.

In the URI, specify the target server ID and the target metadata key.



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

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+
|{key}                     |Metadatakey             |The name of the target   |
|                          |                        |key in a metadata key    |
|                          |                        |pair. A string with      |
|                          |                        |maximum length of 255    |
|                          |                        |characters.              |
+--------------------------+------------------------+-------------------------+


This operation does not accept a request body.

**Example Show server metadata item details: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json

Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**meta**                  |Object                  |Container for a metadata |
|                          |                        |keypair for the          |
|                          |                        |specified server. This   |
|                          |                        |container holds a single |
|                          |                        |keypair using format of  |
|                          |                        |"metadata key" :         |
|                          |                        |"metadata value".        |
+--------------------------+------------------------+-------------------------+
|meta.\ **keyname**        |Keypair                 |Keypair describing the   |
|                          |                        |metadata using format of |
|                          |                        |"keyname" : "keyvalue".  |
+--------------------------+------------------------+-------------------------+


**Example Show server metadata item details: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 32
       Content-Type: application/json
       Date: Tue, 20 Jan 2015 14:07:57 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-85a2fdf4-a6d9-42ce-91bb-2cea8eb5e14e


.. code::

   {
       "meta" : {
           "Label" : "Web"
       }
   }




