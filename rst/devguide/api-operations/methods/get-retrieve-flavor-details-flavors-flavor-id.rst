
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-retrieve-flavor-details-flavors-flavor-id:

Retrieve flavor details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /flavors/{flavor_id}

Retrieves details of the specified flavor.

This operation returns details of the specified flavor in the response body.

Specify the flavor ID in the URI.

The following extensions provide additional information when viewing flavor details:



*  Flavor Extra Data
*  Flavor with extra specs
*  Flavor extra specs
*  Flavor RXTX




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
|{flavor_id}               |Uuid                     |The UUID for the flavor. |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Retrieve flavor details: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json





Response
""""""""""""""""





This table shows the body parameters for the response:

+---------------------------+-------------------------+------------------------+
|Name                       |Type                     |Description             |
+===========================+=========================+========================+
|parameters.\ **flavor**    |Object                   |The container of flavor |
|                           |                         |attributes.             |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\ **OS-  |String                   |The container of flavor |
|FLV-WITH-EXT-              |                         |extra specifications.   |
|SPECS:extra_specs**        |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.OS-FLV-  |String                   |The class for the       |
|WITH-EXT-                  |                         |flavor.                 |
|SPECS:extra_specs.\        |                         |                        |
|**class**                  |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.OS-FLV-  |String                   |The policy class for    |
|WITH-EXT-                  |                         |the flavor.             |
|SPECS:extra_specs.\        |                         |                        |
|**policy_class**           |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.OS-FLV-  |String                   |The io index for the    |
|WITH-EXT-                  |                         |disk.                   |
|SPECS:extra_specs.\        |                         |                        |
|**disk_io_index**          |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.OS-FLV-  |String                   |The policy class for    |
|WITH-EXT-                  |                         |the flavor.             |
|SPECS:extra_specs.\        |                         |                        |
|**number_of_data_disks**   |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\        |String                   |The flavor name.        |
|**name**                   |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\        |String                   |The array of flavor     |
|**links**                  |                         |links for self and      |
|                           |                         |bookmark.               |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.links.\  |Uuid                     |The URL for the flavor  |
|**href**                   |                         |and the associated      |
|                           |                         |``rel``.                |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.links.\  |Uuid                     |The descriptive field   |
|**rel**                    |                         |for the associated      |
|                           |                         |``href``, which is      |
|                           |                         |either ``self`` or      |
|                           |                         |``bookmark``.           |
+---------------------------+-------------------------+------------------------+
|pa\ **ram**eters.flavor.\  |String                   |The amount of RAM.      |
|**ram**                    |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\        |String                   |The number of virtual   |
|**vcpus**                  |                         |CPUs.                   |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\        |String                   |The amount of swap space|
|**swap**                   |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\ **rxtx-|String                   |The rxtx factor, which  |
|factor**                   |                         |describes configured    |
|                           |                         |bandwidth cap values.   |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\ **OS-  |String                   |The number of ephemeral |
|FLV-EXT-DATA:ephemeral**   |                         |disks.                  |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\        |String                   |The disk size.          |
|**disk**                   |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.flavor.\ **id** |String                   |The flavor id.          |
+---------------------------+-------------------------+------------------------+







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




