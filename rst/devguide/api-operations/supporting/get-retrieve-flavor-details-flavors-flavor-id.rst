
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

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

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|flavor                    |Object                   |The container of flavor  |
|                          |                         |attributes.              |
+--------------------------+-------------------------+-------------------------+
|OS-FLV-WITH-EXT-          |String                   |The container of flavor  |
|SPECS:extra_specs         |                         |extra specifications.    |
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
|name                      |String                   |The flavor name.         |
+--------------------------+-------------------------+-------------------------+
|links                     |String                   |The array of flavor      |
|                          |                         |links for self and       |
|                          |                         |bookmark.                |
+--------------------------+-------------------------+-------------------------+
|href                      |Uuid                     |The URL for the flavor   |
|                          |                         |and the associated       |
|                          |                         |``rel``.                 |
+--------------------------+-------------------------+-------------------------+
|rel                       |Uuid                     |The descriptive field    |
|                          |                         |for the associated       |
|                          |                         |``href``, which is       |
|                          |                         |either ``self`` or       |
|                          |                         |``bookmark``.            |
+--------------------------+-------------------------+-------------------------+
|ram                       |String                   |The amount of RAM.       |
+--------------------------+-------------------------+-------------------------+
|vcpus                     |String                   |The number of virtual    |
|                          |                         |CPUs.                    |
+--------------------------+-------------------------+-------------------------+
|swap                      |String                   |The amount of swap space |
+--------------------------+-------------------------+-------------------------+
|rxtx-factor               |String                   |The rxtx factor, which   |
|                          |                         |describes configured     |
|                          |                         |bandwidth cap values.    |
+--------------------------+-------------------------+-------------------------+
|OS-FLV-EXT-DATA:ephemeral |String                   |The number of ephemeral  |
|                          |                         |disks.                   |
+--------------------------+-------------------------+-------------------------+
|disk                      |String                   |The disk size.           |
+--------------------------+-------------------------+-------------------------+
|id                        |String                   |The flavor id.           |
+--------------------------+-------------------------+-------------------------+





**Example Retrieve flavor details: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 528
        Content-Type: application/json
        Date: Wed, 08 Jul 2015 21:38:05 GMT, Wed, 08 Jul 2015 21:38:06 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-3c0027db-484f-4f36-81b7-0b35b556bc78


