.. _get-retrieve-flavor-details-flavors-flavor-id:

Retrieve flavor details
-----------------------

.. code::

    GET /flavors/{flavor_id}

This operation returns details of the specified flavor in the response body.

Specify the flavor ID in the URI.

The following extensions provide additional information when viewing flavor
details:


*  Flavor with extra specs
*  Flavor extra specs


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

+-------------------------+-------------------------+-------------------------+
|Name                     |Type                     |Description              |
+=========================+=========================+=========================+
|{flavor_id}              |Uuid                     |The UUID for the flavor. |
+-------------------------+-------------------------+-------------------------+



This operation does not accept a request body.


**Example Retrieve flavor details: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


Response
^^^^^^^^


This table shows the body parameters for the response:

+---------------------------+------------------------+------------------------+
|Name                       |Type                    |Description             |
+===========================+========================+========================+
|**flavor**                 |Object                  |The container of flavor |
|                           |                        |attributes.             |
+---------------------------+------------------------+------------------------+
|flavor.\ **OS-FLV-WITH-EXT-|String                  |The container of flavor |
|SPECS:extra_specs**        |                        |extra specifications.   |
|                           |                        |                        |
+---------------------------+------------------------+------------------------+
|flavor.OS-FLV-WITH-EXT-    |String                  |The class for the       |
|SPECS:extra_specs.\        |                        |flavor.                 |
|**class**                  |                        |                        |
+---------------------------+------------------------+------------------------+
|flavor.OS-FLV-WITH-EXT-    |String                  |The policy class for    |
|SPECS:extra_specs.\        |                        |the flavor.             |
|**policy_class**           |                        |                        |
+---------------------------+------------------------+------------------------+
|flavor.OS-FLV-WITH-EXT-    |String                  |The io index for the    |
|SPECS:extra_specs.\        |                        |disk.                   |
|**disk_io_index**          |                        |                        |
+---------------------------+------------------------+------------------------+
|flavor.OS-FLV-WITH-EXT-    |String                  |The policy class for    |
|SPECS:extra_specs.\        |                        |the flavor.             |
|**number_of_data_disks**   |                        |                        |
+---------------------------+------------------------+------------------------+
|flavor.\ **name**          |String                  |The flavor name.        |
+---------------------------+------------------------+------------------------+
|flavor.\ **links**         |String                  |The array of flavor     |
|                           |                        |links for self and      |
|                           |                        |bookmark.               |
+---------------------------+------------------------+------------------------+
|flavor.links.\ **href**    |Uuid                    |The URL for the flavor  |
|                           |                        |and the associated      |
|                           |                        |``rel``.                |
+---------------------------+------------------------+------------------------+
|flavor.links.\ **rel**     |Uuid                    |The descriptive field   |
|                           |                        |for the associated      |
|                           |                        |``href``, which is      |
|                           |                        |either ``self`` or      |
|                           |                        |``bookmark``.           |
+---------------------------+------------------------+------------------------+
|flavor.\ **ram**           |String                  |The amount of RAM.      |
|                           |                        |                        |
+---------------------------+------------------------+------------------------+
|flavor.\ **vcpus**         |String                  |The number of virtual   |
|                           |                        |CPUs.                   |
+---------------------------+------------------------+------------------------+
|flavor.\ **swap**          |String                  |The amount of swap space|
|                           |                        |                        |
+---------------------------+------------------------+------------------------+
|flavor.\ **rxtx-factor**   |String                  |The rxtx factor, which  |
|                           |                        |describes configured    |
|                           |                        |bandwidth cap values.   |
+---------------------------+------------------------+------------------------+
|flavor.\ **OS-             |String                  |The number of ephemeral |
|FLV-EXT-DATA:ephemeral**   |                        |disks.                  |
+---------------------------+------------------------+------------------------+
|flavor.\ **disk**          |String                  |The disk size.          |
|                           |                        |                        |
+---------------------------+------------------------+------------------------+
|flavor.\ **id**            |String                  |The flavor id.          |
+---------------------------+------------------------+------------------------+


**Example Retrieve flavor details: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 528
       Content-Type: application/json
       Date: Wed, 08 Jul 2015 21:38:05 GMT, Wed, 08 Jul 2015 21:38:06 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-3c0027db-484f-4f36-81b7-0b35b556bc78


.. code::

   {
       "flavor": {
           "OS-FLV-EXT-DATA:ephemeral": 0,
           "OS-FLV-WITH-EXT-SPECS:extra_specs": {
               "class": "compute1",
               "disk_io_index": "-1",
               "number_of_data_disks": "0",
               "policy_class": "compute_flavor"
           },
           "disk": 0,
           "id": "compute1-15",
           "links": [
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/flavors/compute1-15",
                   "rel": "self"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/820712/flavors/compute1-15",
                   "rel": "bookmark"
               }
           ],
           "name": "15 GB Compute v1",
           "ram": 15360,
           "rxtx_factor": 1250.0,
           "swap": "",
           "vcpus": 8
       }
   }




