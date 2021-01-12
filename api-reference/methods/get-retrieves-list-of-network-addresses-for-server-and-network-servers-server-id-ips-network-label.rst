.. _get-retrieves-list-of-network-addresses-for-server-and-network-servers-server-id-ips-network-label:

Retrieve list of network addresses for server and network
---------------------------------------------------------

.. code::

    GET /servers/{server_id}/ips/{network_label}

This operation retrieves a list of all server and network addresses associated
with the specified server and network.

In the URI, specify the target server ID and target network type ( ``public``
or ``private`` ).


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

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+
|{network_label}           |String                  |The network label, such  |
|                          |                        |as ``public`` or         |
|                          |                        |``private``.             |
+--------------------------+------------------------+-------------------------+


This operation does not accept a request body.

**Example Retrieves list of network addresses for server and network: JSON request**


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
|**nettype**               |Array                   |An array of ``private``  |
|                          |                        |or ``public`` network    |
|                          |                        |address containers.      |
+--------------------------+------------------------+-------------------------+
|nettype.\ **addr**        |Object                  |The IP address.          |
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|nettype.\ **version**     |Object                  |The IP address version,  |
|                          |                        |either ``4`` or ``6``.   |
+--------------------------+------------------------+-------------------------+


**Example Retrieves list of network addresses for server and network: JSON
response**


.. code::

       Status Code: 200 OK
       Content-Length: 121
       Content-Type: application/json
       Date: Fri, 12 Dec 2014 16:59:57 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       X-Compute-Request-Id: req-00daae97-384b-4a57-806c-dd8d2d635287


.. code::

   {
     "public": [
       {
         "version": 6,
         "addr": "2001:4800:7817:0104:7e32:e3ee:ff04:930f"
       },
       {
         "version": 4,
         "addr": "23.253.107.140"
       }
     ]
   }




