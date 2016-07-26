.. _post-create-associated-ip-address-servers-server-id-ip-associations-ipaddressid:

Create associated IP address
----------------------------

.. code::

    POST /servers/{server_id}/ip_associations/{IPAddressID}

This operation creates an associated IP address for the specified server and
already existing IP address ID.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|201                      |                         |                         |
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
|{server_id}              |Uuid                     |The UUID for the server. |
+-------------------------+-------------------------+-------------------------+
|{id}                     |Uuid                     |The Associated IP        |
|                         |                         |address ID, which is not |
|                         |                         |the actual IP address.   |
+-------------------------+-------------------------+-------------------------+


This table shows the body parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|\ **ip_address**          |Array                   |The container for shared |
|                          |                        |IP request parasmeters.  |
+--------------------------+------------------------+-------------------------+
|ip_address.\              |Uuid                    |The ID of the network.   |
|**network_id**            |                        |                         |
+--------------------------+------------------------+-------------------------+
|ip_address.\ **version**  |String                  |The subnet IP version,   |
|                          |                        |which is ``4`` or ``6``. |
+--------------------------+------------------------+-------------------------+
|ip_address.\  **port_ids** Array *(Optional)*      |The array of port        |
|                          |                        |objects, containing port |
|                          |                        |IDs for the shared IP.   |
+--------------------------+------------------------+-------------------------+
|ip_address.\              |Array *(Optional)*      |The array of device      |
|**device_ids**            |                        |objects, containing      |
|                          |                        |device IDs for the       |
|                          |                        |shared IP.               |
+--------------------------+------------------------+-------------------------+

**Example Create associated IP address: JSON request**


.. code::

   {
     "key":"value"
   }


Response
^^^^^^^^

This table shows the body parameters for the response:

+-----------------------------+-----------------------+-----------------------+
|Name                         |Type                   |Description            |
+=============================+=======================+=======================+
|**ip_association**           |Array                  |The container of       |
|                             |                       |associated IP details. |
+-----------------------------+-----------------------+-----------------------+
|ip_association.\ **id**      |Uuid                   |The ID of the          |
|                             |                       |associated IP address. |
+-----------------------------+-----------------------+-----------------------+
|ip_association.\ **address** |Uuid                   |The associatied IP     |
|                             |                       |address.               |
+-----------------------------+-----------------------+-----------------------+

**Example Create associated IP address: JSON response**


.. code::

   {
     "key":"value"
   }




