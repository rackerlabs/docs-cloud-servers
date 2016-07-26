.. _get-retrieve-image-details-images-image-id:

Retrieve image details
----------------------

.. code::

    GET /images/{image_id}

This operation retrieves details of a specified image.

Specify the image ID in the URI.

This operation returns details of the specified image in the response body. The
image_type field in the response indicates whether the image is built-in
``(base)`` or custom ``(snapshot)``.

.. note::
   The response body does not include the serverId field. To retrieve the
   serverId field, get details for all images.

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
|{image_id}                |Uuid                    |The UUID for the image.  |
+--------------------------+------------------------+-------------------------+


This operation does not accept a request body.

**Example Retrieve image details: JSON request**


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
|**image**                 |Object                  |The container of image   |
|                          |                        |details.                 |
+--------------------------+------------------------+-------------------------+
|image.\ **status**        |String                  |The image status, like   |
|                          |                        |``ACTIVE``.              |
+--------------------------+------------------------+-------------------------+
|image.\ **updated**       |Date                    |The date and time that   |
|                          |                        |the image was last       |
|                          |                        |updated.                 |
+--------------------------+------------------------+-------------------------+
|image.\ **links**         |String                  |The array of image links |
|                          |                        |for self and bookmark.   |
+--------------------------+------------------------+-------------------------+
|image.links.\ **href**    |Uuid                    |The URL for the image    |
|                          |                        |and the associated       |
|                          |                        |``rel``.                 |
+--------------------------+------------------------+-------------------------+
|image.links.\ **rel**     |Uuid                    |The descriptive field    |
|                          |                        |for the associated       |
|                          |                        |``href``, which is       |
|                          |                        |either ``self``,         |
|                          |                        |``bookmark``, or         |
|                          |                        |``alternate``.           |
+--------------------------+------------------------+-------------------------+
|image.links.\ **type**    |Uuid                    |The alternate image type.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|image.\ **OS-             |String                  |The disk configuration   |
|DCF:diskConfig**          |                        |value. Valid values are  |
|                          |                        |``AUTO`` and ``MANUAL``. |
+--------------------------+------------------------+-------------------------+
|image.\ **id**            |Uuid                    |The image ID.            |
+--------------------------+------------------------+-------------------------+
|image.\ **OS-             |String                  |The image size.          |
|EXT-IMG-SIZE:size**       |                        |                         |
+--------------------------+------------------------+-------------------------+
|image.\  **name**         |String                  |The image name.          |
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|image.\ **created**       |Date                    |The date and time that   |
|                          |                        |the image was created.   |
+--------------------------+------------------------+-------------------------+
|image.\ **minDisk**       |Int                     |The minimum number of    |
|                          |                        |gigabytes of disk        |
|                          |                        |storage.                 |
+--------------------------+------------------------+-------------------------+
|image.\ **server**        |Object                  |The container of server  |
|                          |                        |attributes for the image.|
+--------------------------+------------------------+-------------------------+
|image.\ **progress**      |Int                     |The completion           |
|                          |                        |percentage for an image. |
|                          |                        |``100`` indicates the    |
|                          |                        |image build is completed.|
+--------------------------+------------------------+-------------------------+
|image.\ **minRam**        |Int                     |The specified minimum    |
|                          |                        |amount of RAM in         |
|                          |                        |megabytes.               |
+--------------------------+------------------------+-------------------------+
|image.\ **metadata**      |Array                   |Array of metadata key    |
|                          |                        |pairs containing         |
|                          |                        |information about the    |
|                          |                        |image.                   |
+--------------------------+------------------------+-------------------------+


**Example Retrieve image details: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 2230
       Content-Type: application/json
       Date: Thu, 09 Jul 2015 18:24:01 GMT, Thu, 09 Jul 2015 18:24:02 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-5ba3fae8-5daf-48c7-9be1-6de842e50ca9


.. code::

   {
     "image": {
       "status": "ACTIVE",
       "updated": "2013-06-07T17:00:39Z",
       "links": [
         {
           "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/images/e3d37ab2-8dc0-4000-b773-b15aad79ad0a",
           "rel": "self"
         },
         {
           "href": "https://dfw.servers.api.rackspacecloud.com/820712/images/e3d37ab2-8dc0-4000-b773-b15aad79ad0a",
           "rel": "bookmark"
         },
         {
           "href": "https://dfw.servers.api.rackspacecloud.com/images/e3d37ab2-8dc0-4000-b773-b15aad79ad0a",
           "type": "application/vnd.openstack.image",
           "rel": "alternate"
         }
       ],
       "OS-DCF:diskConfig": "MANUAL",
       "id": "e3d37ab2-8dc0-4000-b773-b15aad79ad0a",
       "OS-EXT-IMG-SIZE:size": 5562828800,
       "name": "voweb1-firstimage",
       "created": "2013-06-07T16:38:49Z",
       "minDisk": 40,
       "server": {
         "id": "f879f81a-5455-4e57-a0aa-3773e21c2259",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/servers/f879f81a-5455-4e57-a0aa-3773e21c2259",
             "rel": "self"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/820712/servers/f879f81a-5455-4e57-a0aa-3773e21c2259",
             "rel": "bookmark"
           }
         ]
       },
       "progress": 100,
       "minRam": 1024,
       "metadata": {
         "image_type": "snapshot",
         "instance_type_rxtx_factor": "3",
         "auto_disk_config": "False",
         "os_type": "windows"
       }
     }
   }




