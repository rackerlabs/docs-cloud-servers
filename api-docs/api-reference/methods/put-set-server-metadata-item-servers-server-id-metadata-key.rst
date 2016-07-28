.. _put-set-server-metadata-item-servers-server-id-metadata-key:

Set server metadata item
------------------------

.. code::

    PUT /servers/{server_id}/metadata/{key}

This operation creates or replaces metadata item by key for a specified server

In the URI, specify the target server ID and the target metadata key.

In the request body, specify the ``meta`` element, followed by the metadata
key, for example ``version``, with the new value for that key.

.. note::
   The key specified in the request body must match the key specified in the
   URI request.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200                      |Success                  |Request succeeded.       |
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
|{key}                    |Metadatakey              |The name of the target   |
|                         |                         |key in a metadata key    |
|                         |                         |pair. A string with      |
|                         |                         |maximum length of 255    |
|                         |                         |characters.              |
+-------------------------+-------------------------+-------------------------+


This table shows the body parameters for the request:

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


**Example Set server metadata item: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "meta" : {
           "Label" : "Web"
       }
   }


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

**Example Set server metadata item: JSON response**


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
       "meta" : {
           "Label" : "Web"
       }
   }




