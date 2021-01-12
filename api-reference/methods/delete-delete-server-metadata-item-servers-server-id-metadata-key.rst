.. _delete-delete-server-metadata-item-servers-server-id-metadata-key:

Delete server metadata item
---------------------------

.. code::

    DELETE /servers/{server_id}/metadata/{key}

This operation deletes a metadata item by key from the specified server.

If the operation succeeds, it returns an ``HTTP 202`` status code with no
response body.

In the URI, specify the target server ID and the target metadata key.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|204                      |Delete Successful        |Delete request succeeded.|
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

This operation does not accept a request body.

**Example Delete server metadata item: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json

Response
^^^^^^^^

**Example Delete server metadata item: JSON response**


.. code::

       Status Code: 204 OK
       Content-Length: 120
       Content-Type: application/json
       Date: Mon, 19 Jan 2015 23:19:30 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-406a007a-9dfe-4ac4-b819-d64a74244506




