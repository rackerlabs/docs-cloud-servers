.. _get-list-server-metadata-servers-server-id-metadata:

List server metadata
--------------------

.. code::

    GET /servers/{server_id}/metadata

This operation retrieves a list of all metadata for a specified server.

In the URI, specify the target server ID.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200 203                  |Success                  |Request succeeded.       |
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


**Example List server metadata: JSON request**


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
|**metadata**              |Object                  |Container for a metadata |
|                          |                        |keypair for the          |
|                          |                        |specified server. This   |
|                          |                        |container holds one or   |
|                          |                        |more keypairs using      |
|                          |                        |format of "metadata key" |
|                          |                        |: "metadata value".      |
+--------------------------+------------------------+-------------------------+
|metadata.\ **keyname**    |Keypair                 |Keypairs edcribing the   |
|                          |                        |metadata using format of |
|                          |                        |"keyname" : "keyvalue".  |
+--------------------------+------------------------+-------------------------+


**Example List server metadata: JSON response**


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
       "metadata": {
           "Label" : "Web",
           "Version" : "2.1"
       }
   }




