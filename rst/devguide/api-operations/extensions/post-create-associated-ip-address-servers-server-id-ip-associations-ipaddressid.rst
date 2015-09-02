
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
|ip_address                |Array *(Required)*       |The container for shared |
|                          |                         |IP request parasmeters.  |
+--------------------------+-------------------------+-------------------------+
|network_id                |Uuid *(Required)*        |The ID of the network.   |
+--------------------------+-------------------------+-------------------------+
|version                   |String *(Required)*      |The subnet IP version,   |
|                          |                         |which is ``4`` or ``6``. |
+--------------------------+-------------------------+-------------------------+
|port_ids                  |Array *(Optional)*       |The array of port        |
|                          |                         |objects, containing port |
|                          |                         |IDs for the shared IP.   |
+--------------------------+-------------------------+-------------------------+
|device_ids                |Array *(Optional)*       |The array of device      |
|                          |                         |objects, containing      |
|                          |                         |device IDs for the       |
|                          |                         |shared IP.               |
+--------------------------+-------------------------+-------------------------+





**Example Create associated IP address: JSON request**


.. code::

   {
     "key":"value" 
   }




The container for shared IP request parasmeters.

The ID of the network.

The subnet IP version, which is ``4`` or ``6``.

The array of port objects, containing port IDs for the shared IP.

The array of device objects, containing device IDs for the shared IP.




Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|ip_association            |Array                    |The container of         |
|                          |                         |associated IP details.   |
+--------------------------+-------------------------+-------------------------+
|id                        |Uuid                     |The ID of the associated |
|                          |                         |IP address.              |
+--------------------------+-------------------------+-------------------------+
|address                   |Uuid                     |The associatied IP       |
|                          |                         |address.                 |
+--------------------------+-------------------------+-------------------------+







**Example Create associated IP address: JSON response**


.. code::

   {
     "key":"value" 
   }




The container of associated IP details.

The ID of the associated IP address.

The associatied IP address.



