.. _get-show-network-os-networksv2-id:

Show network
------------

.. code::

    GET /os-networksv2/{id}

This operation shows information for the network specified in the request URI.


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
|{id}                     |Uuid                     |The network ID.          |
+-------------------------+-------------------------+-------------------------+

This operation does not accept a request body.


Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**network**               |Object                  |A container of network   |
|                          |                        |details.                 |
+--------------------------+------------------------+-------------------------+
|network.\ **cidr**        |String                  |The CIDR for an isolated |
|                          |                        |network.                 |
+--------------------------+------------------------+-------------------------+
|network.\  **id**         |String                  |The network ID.          |
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|network.\ **label**       |String                  |The name of the network. |
|                          |                        |ServiceNet is labeled as |
|                          |                        |private and PublicNet is |
|                          |                        |labeled as public in the |
|                          |                        |network list.            |
+--------------------------+------------------------+-------------------------+


**Example Show network: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 114
        Content-Type: application/json
        Date: Mon, 13 Apr 2015 20:50:28 GMT, Mon, 13 Apr 2015 20:50:28 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-bc7ab5c9-4a70-4a19-9189-e8f8884e8ae9


.. code::

   {
       "network": {
           "cidr": "192.168.0.0/24",
           "id": "f212726e-6321-4210-9bae-a13f5a33f83f",
           "label": "superprivate_xml"
       }
   }




