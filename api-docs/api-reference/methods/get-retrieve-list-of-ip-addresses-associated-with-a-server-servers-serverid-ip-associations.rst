.. _get-retrieve-list-of-ip-addresses-associated-with-a-server-servers-server-id-ip-associations:

Retrieve list of IP addresses associated with a server
------------------------------------------------------

.. code::

    GET /servers/{server_id}/ip_associations

This operation retrieves a list of all IP addresses associated to the specified
server.



This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200                      |                         |                         |
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

This operation does not accept a request body.

Response
^^^^^^^^

This table shows the body parameters for the response:

+------------------------------+----------------------+-----------------------+
|Name                          |Type                  |Description            |
+==============================+======================+=======================+
|**ip_associations**           |Array                 |The array of IP        |
|                              |                      |associations.          |
+------------------------------+----------------------+-----------------------+
|ip_associations.\             |Uuid                  |The ID of the          |
|**id**                        |                      |associated IP address. |
+------------------------------+----------------------+-----------------------+
|ip_associations.\             |Uuid                  |The associatied IP     |
|**address**                   |                      |address.               |
+------------------------------+----------------------+-----------------------+


**Example Retrieve list of IP addresses associated with a server: JSON
response**


.. code::

   {
       "ip_associations":
       [
           {
               "id": "1",
               "address": "10.1.1.1"
           },
           {
               "id": "2",
               "address": "10.1.1.2"
           }
       ]
   }




