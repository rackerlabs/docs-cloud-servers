.. _post-create-virtual-interface-and-attach-to-server-servers-server-id-os-virtual-interfacesv2:

Create virtual interface and attach to server
---------------------------------------------

.. code::

    POST /servers/{server_id}/os-virtual-interfacesv2

This operation creates a virtual interface for a network and attaches the
network to a server instance.

.. note::
   You can create a maximum of one virtual interface per instance per network.


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

+--------------------------------+---------------------+----------------------+
|Name                            |Type                 |Description           |
+================================+=====================+======================+
|**virtual_interface**           |Object               |A container with      |
|                                |                     |virtual interface     |
|                                |                     |information.          |
+--------------------------------+---------------------+----------------------+
|virtual_interface.\             |Uuid                 |The interface network |
|**network_id**                  |                     |ID.                   |
+--------------------------------+---------------------+----------------------+

**Example Create virtual interface and attach to server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
      "virtual_interface":
       {
         "network_id": "1f7920d3-0e63-4fec-a1cb-f7916671e8eb"
       }
   }


Response
^^^^^^^^

This table shows the body parameters for the response:

+----------------------------------------------+-------------+----------------+
|Name                                          |Type         |Description     |
+==============================================+=============+================+
|**virtual_interfaces**                        |Array        |The array of    |
|                                              |             |virtual         |
|                                              |             |interfaces.     |
+----------------------------------------------+-------------+----------------+
|virtual_interfaces.\ **id**                   |String       |The virtual     |
|                                              |             |interface ID.   |
+----------------------------------------------+-------------+----------------+
|virtual_interfaces.\ **ip_addresses**         |Array        |The array of    |
|                                              |             |interface IP    |
|                                              |             |address details.|
+----------------------------------------------+-------------+----------------+
|virtual_interfaces.ip_addresses\ **address**  |String       |The interface   |
|                                              |             |IP address.     |
+----------------------------------------------+-------------+----------------+
|virtual_interfaces.ip_addresses.\             |Uuid         |The interface   |
|**network_id**                                |             |network ID.     |
+----------------------------------------------+-------------+----------------+
|virtual_interfaces.ip_addresses.\             |String       |The interface   |
|**network_label**                             |             |network label.  |
+----------------------------------------------+-------------+----------------+
|virtual_interfaces.\ **mac_address**          |String       |The Media       |
|                                              |             |Access Control  |
|                                              |             |(MAC) address   |
|                                              |             |for the virtual |
|                                              |             |interface. A    |
|                                              |             |MAC address is  |
|                                              |             |a unique        |
|                                              |             |identifier      |
|                                              |             |assigned to     |
|                                              |             |network         |
|                                              |             |interfaces for  |
|                                              |             |communications  |
|                                              |             |on the physical |
|                                              |             |network segment.|
+----------------------------------------------+-------------+----------------+

**Example Create virtual interface and attach to server: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 247
       Content-Type: application/json
       Date: Wed, 08 Apr 2015 18:03:16 GMT, Wed, 08 Apr 2015 18:03:23 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-f28cbcae-fe5e-4318-908a-dd6a9cb23122


.. code::

   {
      "virtual_interfaces":[
         {
            "mac_address":"FE:ED:FA:00:08:93",
            "id":"045f195f-3347-487b-8e80-8ee3390eda56",
            "ip_addresses":[
               {
                  "address":"192.168.0.1",
                  "network_id":"196a0246-86cc-46fa-9ecf-850f67c2cb7c",
                  "network_label":"added_network"
               }
            ]
         }
      ]
   }




