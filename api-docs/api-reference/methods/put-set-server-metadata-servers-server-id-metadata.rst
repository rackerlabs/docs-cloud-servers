.. _put-set-server-metadata-servers-server-id-metadata:

Set server metadata
-------------------

.. code::

    PUT /servers/{server_id}/metadata

This operation creates or replaces metadata items for a specified server

You can add or update one or more new metadata items in a single request.

If metadata items in the request body do not exist, they are created. If they
do exist, they are replaced.

.. important::
   Existing metadata items are replaced with the ones provided in the request
   regardless of the names of the original metadata items.


If you exceed the maximum number of metadata items in the request, the call
throws an ``overLimit (413)`` fault. To find the maximum number of key-value
pairs that can be supplied for each server, use the maxServerMeta absolute
limit query.

In the URI, specify the target server ID.

In the request body, specify the ``metadata`` element, followed by the new
metadata key, for example ``version``, with the value for that key.



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

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+

This table shows the body parameters for the request:

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


**Example Set server metadata: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "metadata": {
           "Label" : "Web",
           "Version" : "2.1"
       }
   }





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


**Example Set server metadata: JSON response**


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

