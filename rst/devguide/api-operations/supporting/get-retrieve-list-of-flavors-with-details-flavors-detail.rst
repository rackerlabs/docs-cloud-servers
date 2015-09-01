
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve list of flavors with details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /flavors/detail

Retrieves all details for all available flavors.

This operation returns details of all flavors in the response body.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Success                  |Request succeeded.       |
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




This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|minDisk                   |Int *(Optional)*         |Filters the list of      |
|                          |                         |flavors to those with    |
|                          |                         |the specified minimum    |
|                          |                         |number of gigabytes of   |
|                          |                         |disk storage.            |
+--------------------------+-------------------------+-------------------------+
|minRam                    |Int *(Optional)*         |Filters the list of      |
|                          |                         |flavors to those with    |
|                          |                         |the specified minimum    |
|                          |                         |amount of RAM in         |
|                          |                         |megabytes.               |
+--------------------------+-------------------------+-------------------------+
|marker                    |String *(Optional)*      |The ID of the last item  |
|                          |                         |in the previous list.    |
+--------------------------+-------------------------+-------------------------+
|limit                     |Int *(Optional)*         |Sets the page size.      |
+--------------------------+-------------------------+-------------------------+




This operation does not accept a request body.




**Example Retrieve list of flavors with details: JSON request**


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
|flavors                   |Array                    |The container of flavor  |
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





**Example Retrieve list of flavors with details: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 18360
        Content-Type: application/json
        Date: Fri, 10 Jul 2015 18:27:40 GMT, Fri, 10 Jul 2015 18:27:40 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-63cec0f7-a82d-426c-91ce-296bb66d7f74


