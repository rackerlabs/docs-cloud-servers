
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-list-extra-specs-for-flavors-flavors-flavor-id-os-extra-specs:

List extra specs for flavors
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /flavors/{flavor_id}/os-extra_specs

Retrieves flavor extra specs.

This operation shows extra specifications for flavors.

In the URI, specify the flavor ID.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200 203                   |Success                  |Request succeeded.       |
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
|{flavor_id}               |String                   |The flavor id.           |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example List extra specs for flavors: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json





Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|extra_specs               |Object                   |The container for flavor |
|                          |                         |extra specification      |
|                          |                         |details.                 |
+--------------------------+-------------------------+-------------------------+
|class                     |String                   |The class for the flavor.|
+--------------------------+-------------------------+-------------------------+
|policy_class              |String                   |The policy class for the |
|                          |                         |flavor.                  |
+--------------------------+-------------------------+-------------------------+
|disk_io_index             |String                   |The io index for the     |
|                          |                         |disk.                    |
+--------------------------+-------------------------+-------------------------+
|number_of_data_disks      |String                   |The policy class for the |
|                          |                         |flavor.                  |
+--------------------------+-------------------------+-------------------------+







**Example List extra specs for flavors: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 124
       Content-Type: application/json
       Date: Wed, 08 Jul 2015 15:58:25 GMT, Wed, 08 Jul 2015 15:58:25 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-5b690cfe-c1c7-4749-b0b1-cedf92d378dc


.. code::

   {
     "extra_specs": {
       "policy_class": "general_flavor",
       "class": "general1",
       "disk_io_index": "40",
       "number_of_data_disks": "0"
     }
   }




