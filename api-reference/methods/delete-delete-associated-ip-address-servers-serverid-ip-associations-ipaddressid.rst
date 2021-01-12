.. _delete-delete-associated-ip-address-servers-server-id-ip-associations-ipaddressid:

Delete associated IP address
----------------------------

.. code::

    DELETE /servers/{server_id}/ip_associations/{IPAddressID}

This operation deletes the specified associated IP address, using the
associated IP address ID.

This table shows the possible response codes for this operation:

+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|204                      |                         |                         |
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

This operation does not accept a request body.

Response
^^^^^^^^

**Example Delete associated IP address: JSON response**


.. code::

   Content-Type: application/json
   Accept: application/json
   status: 204




