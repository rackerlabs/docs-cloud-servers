
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _post-create-associated-ip-address-servers-server-id-ip-associations-ipaddressid:

Create associated IP address
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /servers/{server_id}/ip_associations/{IPAddressID}

Creates a associated IP on a specified network.

This operation creates an associated IP address for the specified server and already existing IP address 				ID.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|201                       |                         |                         |
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




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{server_id}               |Uuid                     |The UUID for the server. |
+--------------------------+-------------------------+-------------------------+
|{id}                      |Uuid                     |The Associated IP        |
|                          |                         |address ID, which is not |
|                          |                         |the actual IP address.   |
+--------------------------+-------------------------+-------------------------+





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|parameters.\              |Array *(Required)*       |The container for shared |
|**ip_address**            |                         |IP request parasmeters.  |
+--------------------------+-------------------------+-------------------------+
|parameters.ip_address.\   |Uuid *(Required)*        |The ID of the network.   |
|**network_id**            |                         |                         |
+--------------------------+-------------------------+-------------------------+
|parameters.ip_address.\   |String *(Required)*      |The subnet IP version,   |
|**version**               |                         |which is ``4`` or ``6``. |
+--------------------------+-------------------------+-------------------------+
|parameters.ip_address.\   |Array *(Optional)*       |The array of port        |
|**port_ids**              |                         |objects, containing port |
|                          |                         |IDs for the shared IP.   |
+--------------------------+-------------------------+-------------------------+
|parameters.ip_address.\   |Array *(Optional)*       |The array of device      |
|**device_ids**            |                         |objects, containing      |
|                          |                         |device IDs for the       |
|                          |                         |shared IP.               |
+--------------------------+-------------------------+-------------------------+





**Example Create associated IP address: JSON request**


.. code::

   {
     "key":"value" 
   }





Response
""""""""""""""""





This table shows the body parameters for the response:

+-----------------------------+------------------------+-----------------------+
|Name                         |Type                    |Description            |
+=============================+========================+=======================+
|parameters.\                 |Array                   |The container of       |
|**ip_association**s          |                        |associated IP details. |
+-----------------------------+------------------------+-----------------------+
|parameters.ip_association.\  |Uuid                    |The ID of the          |
|**id**                       |                        |associated IP address. |
+-----------------------------+------------------------+-----------------------+
|parameters.ip_association.\  |Uuid                    |The associatied IP     |
|**address**                  |                        |address.               |
+-----------------------------+------------------------+-----------------------+







**Example Create associated IP address: JSON response**


.. code::

   {
     "key":"value" 
   }




