
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Create associated ip address
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /servers/{serverID}/ip_associations/{IPAddressID}

This operation creates an associated IP address for the specified server and already existing 
IP address ID.



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
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{id}                      |Uuid                     |The Associated IP        |
|                          |                         |address ID, which is not |
|                          |                         |the actual IP address.   |
+--------------------------+-------------------------+-------------------------+


This table shows the body parameters for the request:

+---------------------------+-------------------------+-------------------------+
|Name                       |Type                     |Description              |
+===========================+=========================+=========================+
|**ip_address**             |Array *(Required)*       |The container for shared |
|                           |                         |IP request parasmeters.  |
+---------------------------+-------------------------+-------------------------+
|ip_address.\ **network_id**|Uuid *(Required)*        |The ID of the network.   |
+---------------------------+-------------------------+-------------------------+
|ip_address.\ **version**   |String *(Required)*      |The subnet IP version,   |
|                           |                         |which is ``4`` or ``6``. |
+---------------------------+-------------------------+-------------------------+
|ip_address.\ **port_ids**  |Array *(Optional)*       |The array of port        |
|                           |                         |objects, containing port |
|                           |                         |IDs for the shared IP.   |
+---------------------------+-------------------------+-------------------------+
|ip_address.\ **device_ids**|Array *(Optional)*       |The array of device      |
|                           |                         |objects, containing      |
|                           |                         |device IDs for the       |
|                           |                         |shared IP.               |
+---------------------------+-------------------------+-------------------------+


**Example Create associated ip address: JSON request**


.. code::

    {
      "key":"value" 
    }


Response
""""""""""""""""


This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**ip_association**        |Array                    |The container of         |
|                          |                         |associated IP details.   |
+--------------------------+-------------------------+-------------------------+
|ip_association.\ **id**   |Uuid                     |The ID of the associated |
|                          |                         |IP address.              |
+--------------------------+-------------------------+-------------------------+
|ip_association.\          |Uuid                     |The associatied IP       |
|**address**               |                         |address.                 |
+--------------------------+-------------------------+-------------------------+


**Example Create associated ip address: JSON response**


.. code::

    {
      "key":"value" 
    }


