.. _get-retrieve-list-of-flavors-with-details-flavors-detail:

Retrieve list of flavors with details
-------------------------------------

.. code::

    GET /flavors/detail

This operation returns details of all flavors in the response body.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200                      |Success                  |Request succeeded.       |
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

This table shows the query parameters for the request:

+-------------------------+-------------------------+-------------------------+
|Name                     |Type                     |Description              |
+=========================+=========================+=========================+
|minDisk                  |Int                      |Filters the list of      |
|                         |                         |flavors to those with    |
|                         |                         |the specified minimum    |
|                         |                         |number of gigabytes of   |
|                         |                         |disk storage.            |
+-------------------------+-------------------------+-------------------------+
|minRam                   |Int                      |Filters the list of      |
|                         |                         |flavors to those with    |
|                         |                         |the specified minimum    |
|                         |                         |amount of RAM in         |
|                         |                         |megabytes.               |
+-------------------------+-------------------------+-------------------------+
|marker                   |String                   |The ID of the last item  |
|                         |                         |in the previous list.    |
+-------------------------+-------------------------+-------------------------+
|limit                    |Int                      |Sets the page size.      |
+-------------------------+-------------------------+-------------------------+

This operation does not accept a request body.

**Example Retrieve list of flavors with details: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json

Response
^^^^^^^^

This table shows the body parameters for the response:

+----------------------------+-----------------------+------------------------+
|Name                        |Type                   |Description             |
+============================+=======================+========================+
|flavor                      |Array                  |The container of flavor |
|                            |                       |attributes.             |
+----------------------------+-----------------------+------------------------+
|flavors.\ **OS-             |String                 |The container of flavor |
|FLV-WITH-EXT-               |                       |extra specifications.   |
|SPECS:extra_specs**         |                       |                        |
+----------------------------+-----------------------+------------------------+
|flavors.OS-FLV-WITH-EXT-    |String                 |The class for the       |
|SPECS:extra_specs.\         |                       |flavor.                 |
|**class**                   |                       |                        |
+----------------------------+-----------------------+------------------------+
|flavors.OS-FLV-WITH-EXT-    |String                 |The policy class for    |
|SPECS:extra_specs.\         |                       |the flavor.             |
|**policy_class**            |                       |                        |
+----------------------------+-----------------------+------------------------+
|flavors.OS-FLV-WITH-EXT-    |String                 |The io index for the    |
|SPECS:extra_specs.\         |                       |disk.                   |
|**disk_io_index**           |                       |                        |
+----------------------------+-----------------------+------------------------+
|flavors.OS-FLV-WITH-EXT-    |String                 |The policy class for    |
|SPECS:extra_specs.\         |                       |the flavor.             |
|**number_of_data_disks**    |                       |                        |
+----------------------------+-----------------------+------------------------+
|flavors.\ **name**          |String                 |The flavor name.        |
+----------------------------+-----------------------+------------------------+
|flavors.\ **links**         |String                 |The array of flavor     |
|                            |                       |links for self and      |
|                            |                       |bookmark.               |
+----------------------------+-----------------------+------------------------+
|flavors.links.\ **href**    |Uuid                   |The URL for the flavor  |
|                            |                       |and the associated      |
|                            |                       |``rel``.                |
+----------------------------+-----------------------+------------------------+
|flavors.links.\ **rel**     |Uuid                   |The descriptive field   |
|                            |                       |for the associated      |
|                            |                       |``href``, which is      |
|                            |                       |either ``self`` or      |
|                            |                       |``bookmark``.           |
+----------------------------+-----------------------+------------------------+
|flavors.\ **ram**           |String                 |The amount of RAM.      |
|                            |                       |                        |
+----------------------------+-----------------------+------------------------+
|flavors.\ **vcpus**         |String                 |The number of virtual   |
|                            |                       |CPUs.                   |
+----------------------------+-----------------------+------------------------+
|flavors.\ **swap**          |String                 |The amount of swap space|
+----------------------------+-----------------------+------------------------+
|flavors.\ **rxtx-factor**   |String                 |The rxtx factor, which  |
|                            |                       |describes configured    |
|                            |                       |bandwidth cap values.   |
+----------------------------+-----------------------+------------------------+
|flavors.\ **OS-             |String                 |The number of ephemeral |
|FLV-EXT-DATA:ephemeral**    |                       |disks.                  |
+----------------------------+-----------------------+------------------------+
|flavors.\ **disk**          |String                 |The disk size.          |
|                            |                       |                        |
+----------------------------+-----------------------+------------------------+
|flavors.\ **id**            |String                 |The flavor id.          |
+----------------------------+-----------------------+------------------------+

**Example Retrieve list of flavors with details: JSON response**


The following example shows only a few images in the list for brevity.

.. code::

       Status Code: 200 OK
       Content-Length: 18360
       Content-Type: application/json
       Date: Fri, 10 Jul 2015 18:27:40 GMT, Fri, 10 Jul 2015 18:27:40 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-63cec0f7-a82d-426c-91ce-296bb66d7f74


.. code::

   {
     "flavors": [
         {
         "OS-FLV-WITH-EXT-SPECS:extra_specs": {
           "resize_policy_class": "performance_flavor",
           "policy_class": "performance_flavor",
           "class": "performance2",
           "disk_io_index": "60",
           "number_of_data_disks": "2"
         },
         "name": "60 GB Performance",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/flavors/performance2-60",
             "rel": "self"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/820712/flavors/performance2-60",
             "rel": "bookmark"
           }
         ],
         "ram": 61440,
         "vcpus": 16,
         "swap": "",
         "rxtx_factor": 5000,
         "OS-FLV-EXT-DATA:ephemeral": 600,
         "disk": 40,
         "id": "performance2-60"
       },
         {
         "OS-FLV-WITH-EXT-SPECS:extra_specs": {
           "resize_policy_class": "performance_flavor",
           "policy_class": "performance_flavor",
           "class": "performance2",
           "disk_io_index": "70",
           "number_of_data_disks": "3"
         },
         "name": "90 GB Performance",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/flavors/performance2-90",
             "rel": "self"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/820712/flavors/performance2-90",
             "rel": "bookmark"
           }
         ],
         "ram": 92160,
         "vcpus": 24,
         "swap": "",
         "rxtx_factor": 7500,
         "OS-FLV-EXT-DATA:ephemeral": 900,
         "disk": 40,
         "id": "performance2-90"
       }
     ]
   }




