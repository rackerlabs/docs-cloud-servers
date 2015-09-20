
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Show associated ip address
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /servers/{serverID}/ip_associations/{IPAddressID}

This operation retrieves information for an associated IP address, using the associated IP 
address ID.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |                         |                         |
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





This operation does not accept a request body.




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





**Example Show associated ip address: JSON response**


.. code::

    {
        "ip_association": 
        {
            "id": "1", 
            "address": "10.1.1.1"
        }
    }


