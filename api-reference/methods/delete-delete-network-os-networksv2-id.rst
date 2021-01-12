.. _delete-delete-network-os-networksv2-id:

Delete network
--------------

.. code::

    DELETE /os-networksv2/{id}

This operation deletes the network specified in the request URI.

.. note::
   You can delete an isolated network only if it is not attached to any server.
   To detach a network from a server, delete the virtual interface for the
   network from the server instance.

This table shows the possible response codes for this operation:

+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|202                      |Delete Successful        |Delete request succeeded.|
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
|{id}                     |Uuid                     |The network ID.          |
+-------------------------+-------------------------+-------------------------+

This operation does not accept a request body.

**Example Delete network: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json

Response
^^^^^^^^

**Example Delete network: JSON response**


.. code::

        Status Code: 202 Accepted
        Content-Length: 58
        Content-Type: text/plain; charset=UTF-8
        Date: Tue, 14 Apr 2015 13:09:59 GMT, Tue, 14 Apr 2015 13:10:01 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-33b4fead-66a2-420e-b864-bc117d609a85




