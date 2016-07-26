.. _get-retrieve-list-of-networks-os-networksv2:

Retrieve list of networks
-------------------------

.. code::

    GET /os-networksv2

This operation retrieves a list of the networks configured for the tenant ID
specified in the request URI.


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

This operation does not accept a request body.


**Example Retrieves list of networks: JSON request**


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
|**networks**              |Array                   |An array of networks.    |
+--------------------------+------------------------+-------------------------+
|networks.\ **cidr**       |String                  |The CIDR for an isolated |
|                          |                        |network. This parameter  |
|                          |                        |is not included for      |
|                          |                        |PublicNet and ServiceNet.|
+--------------------------+------------------------+-------------------------+
|networks.\ **id**         |String                  |The network ID.          |
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|networks.\  **label**     |String                  |The name of the network. |
|                          |                        |ServiceNet is labeled as |
|                          |                        |private, and PublicNet   |
|                          |                        |is labeled as public in  |
|                          |                        |the network list.        |
+--------------------------+------------------------+-------------------------+


**Example Retrieve list of networks: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 474
       Content-Type: application/json
       Date: Mon, 13 Apr 2015 18:41:07 GMT, Mon, 13 Apr 2015 18:41:08 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-889f3f67-e02e-416c-9d91-9e3bb33e766d


.. code::

   {
      "networks":[
         {
            "cidr":"192.168.0.0/24",
            "id":"1f84c238-b05a-4374-a0cb-aa6140032cd1",
            "label":"new_network"
         },
         {
            "id":"00000000-0000-0000-0000-000000000000",
            "label":"public"
         },
         {
            "id":"11111111-1111-1111-1111-111111111111",
            "label":"private"
         }
      ]
   }




