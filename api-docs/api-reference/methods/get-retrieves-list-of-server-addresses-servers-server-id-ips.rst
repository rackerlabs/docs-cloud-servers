.. _get-retrieves-list-of-server-addresses-servers-server-id-ips:

Retrieves list of server addresses
----------------------------------

.. code::

    GET /servers/{server_id}/ips

This operation retrieves a list of all server and network addresses associated
with the specified server.

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

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+

This operation does not accept a request body.

**Example Retrieves list of server addresses: JSON request**


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
|**addresses**                   |Object               |A container for one   |
|                                |                     |or more server        |
|                                |                     |details to be updated.|
+--------------------------------+---------------------+----------------------+
|addresses.\ **nettype**         |Object               |An array of           |
|                                |                     |``private`` or        |
|                                |                     |``public`` network    |
|                                |                     |address containers.   |
+--------------------------------+---------------------+----------------------+
|addresses.nettype.\ **addr**    |Object               |The IP address.       |
|                                |                     |                      |
+--------------------------------+---------------------+----------------------+
|addresses.nettype.\ **version** |Object               |The IP address        |
|                                |                     |version, either ``4`` |
|                                |                     |or ``6``.             |
+--------------------------------+---------------------+----------------------+

**Example Retrieves list of server addresses: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 191
       Content-Type: application/json
       Date: Fri, 12 Dec 2014 16:37:29 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       X-Compute-Request-Id: req-624fa036-8f73-4ca9-aa22-428df756c578


.. code::

   {
     "addresses": {
       "public": [
         {
           "version": 6,
           "addr": "2001:4800:7817:0104:7e32:e3ee:ff04:930f"
         },
         {
           "version": 4,
           "addr": "23.253.107.140"
         }
       ],
       "private": [
         {
           "version": 4,
           "addr": "10.208.196.170"
         }
       ]
     }
   }




