
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _post-create-network-os-networksv2:

Create network
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /os-networksv2

Creates a network for the specified tenant ID.

This operation creates a network for the tenant ID specified in the request URI.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Success                  |Request succeeded.       |
+--------------------------+-------------------------+-------------------------+
|400                       |Error                    |A general error has      |
|                          |                         |occured.                 |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |Unauthorized.            |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Forbidden.               |
+--------------------------+-------------------------+-------------------------+
|405                       |Bad Method               |Bad method.              |
+--------------------------+-------------------------+-------------------------+
|409                       |Conflicting Reqest       |Conflicting request.     |
+--------------------------+-------------------------+-------------------------+
|413                       |Over Limit               |The number of items      |
|                          |                         |returned is above the    |
|                          |                         |allowed limit.           |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This table shows the body parameters for the request:

+----------------------+-------------+----------------------------------------------------------+
|Name                  |Type         |Description                                               |
+======================+=============+==========================================================+
|parameters.\          |Object       |A container of network details.                           |
|**network**           |*(Required)* |                                                          |
+----------------------+-------------+----------------------------------------------------------+
|parameters.network.\  |Uuid         |The IP block from which to allocate the network. For      |
|**cidr**              |*(Required)* |example, 172.16.0.0/24 or 2001:DB8::/64. For more         |
|                      |             |information about CIDR notation, see ` Using CIDR         |
|                      |             |Notation in Cloud Networks                                |
|                      |             |<http://www.rackspace.com/knowledge_center/article/using- |
|                      |             |cidr-notation>`__ in the Knowledge Center.                |
+----------------------+-------------+----------------------------------------------------------+
|parameters.network.\  |String       |The name of the new network. For example, my_new_network. |
|**label**             |*(Required)* |                                                          |
+----------------------+-------------+----------------------------------------------------------+





**Example Create network: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "network": 
           {
               "cidr": "192.168.0.0/24", 
               "label": "superprivate"
           }
   }





Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|parameters.\ **network**  |Object                   |A container of network   |
|                          |                         |details.                 |
+--------------------------+-------------------------+-------------------------+
|parameters.network.\      |String                   |The CIDR for an isolated |
|**cidr**                  |                         |network.                 |
+--------------------------+-------------------------+-------------------------+
|parameters.network.\      |String                   |The network ID.          |
|**id**                    |                         |                         |
+--------------------------+-------------------------+-------------------------+
|parameters.network.\      |String                   |The name of the network. |
|**label**                 |                         |ServiceNet is labeled as |
|                          |                         |private and PublicNet is |
|                          |                         |labeled as public in the |
|                          |                         |network list.            |
+--------------------------+-------------------------+-------------------------+







**Example Create network: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 110
        Content-Type: application/json
        Date: Mon, 13 Apr 2015 19:04:21 GMT, Mon, 13 Apr 2015 19:04:24 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-175c37e9-60a7-42de-9922-5bf95644dad2


.. code::

   {
       "network": {
           "cidr": "192.168.0.0/24", 
           "id": "1ff4489e-db0e-45a6-8c9f-4616c6ef5db1", 
           "label": "superprivate"
       }
   }




