.. _get-show-flavor-with-extra-specs-flavors-flavor-id:

Show flavor with extra specs
----------------------------

.. code::

    GET /flavors/{flavor_id}

This operation shows extra specifications for the flavor, such as identifying
the policy class, in the flavor operations.

In the URI, specify the flavor ID.


This table shows the possible response codes for this operation:

+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200 203                  |Success                  |Request succeeded.       |
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
|{flavor_id}               |String                  |The flavor id.           |
+--------------------------+------------------------+-------------------------+


This operation does not accept a request body.

**Example Show flavor with extra specs: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**extra_specs**           |Object                  |The container for flavor |
|                          |                        |extra specification      |
|                          |                        |details.                 |
+--------------------------+------------------------+-------------------------+
|extra_specs.\ **class**   |String                  |The class for the flavor.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|extra_specs.\             |String                  |The policy class for the |
|**policy_class**          |                        |flavor.                  |
+--------------------------+------------------------+-------------------------+
|extra_specs.\             |String                  |The io index for the     |
|**disk_io_index**         |                        |disk.                    |
+--------------------------+------------------------+-------------------------+
|extra_specs.\             |String                  |The policy class for the |
|**number_of_data_disks**  |                        |flavor.                  |
+--------------------------+------------------------+-------------------------+


**Example Show flavor with extra specs: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 124
       Content-Type: application/json
       Date: Tue, 27 Jan 2015 13:46:52 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-7c63f55b-9b16-49d2-854c-dfecfc362116


.. code::

   {
     "extra_specs": {
       "policy_class": "compute_flavor",
       "class": "compute1",
       "disk_io_index": "-1",
       "number_of_data_disks": "0"
     }
   }




