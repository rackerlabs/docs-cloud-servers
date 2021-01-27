.. _get-retrieve-list-of-images-with-details-images-detail:

Retrieve list of images with details
------------------------------------

.. code::

    GET /images/detail

This operation returns details of all images in the response body.

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
|server                   |Object                   |Filters the list of      |
|                         |                         |images by server.        |
|                         |                         |Specify the server       |
|                         |                         |reference by ID or by    |
|                         |                         |full URL.                |
+-------------------------+-------------------------+-------------------------+
|name                     |String                   |Filters the list of      |
|                         |                         |images by image name.    |
+-------------------------+-------------------------+-------------------------+
|status                   |Imagestatus              |Filters the list of      |
|                         |                         |images by status. In-    |
|                         |                         |flight images have a     |
|                         |                         |status of SAVING and the |
|                         |                         |conditional progress     |
|                         |                         |element contains a value |
|                         |                         |from 0 to 100, which     |
|                         |                         |indicates the percentage |
|                         |                         |completion. Other        |
|                         |                         |possible values for the  |
|                         |                         |status attribute include |
|                         |                         |ACTIVE, DELETED, ERROR,  |
|                         |                         |SAVING, and UNKNOWN.     |
|                         |                         |Images with an ACTIVE    |
|                         |                         |status are available for |
|                         |                         |use.                     |
+-------------------------+-------------------------+-------------------------+
|changes-since            |Datetime                 |Filters the list of      |
|                         |                         |images to those that     |
|                         |                         |have changed since the   |
|                         |                         |changes-since time.      |
+-------------------------+-------------------------+-------------------------+
|marker                   |Uuid                     |The ID of the last item  |
|                         |                         |in the previous list.    |
+-------------------------+-------------------------+-------------------------+
|limit                    |Int                      |Sets the page size.      |
+-------------------------+-------------------------+-------------------------+
|type                     |String                   |Filters Rackspace base   |
|                         |                         |images or any custom     |
|                         |                         |server images that you   |
|                         |                         |have created.            |
+-------------------------+-------------------------+-------------------------+

This operation does not accept a request body.

**Example Retrieve list of images with details: JSON request**


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
|**images**                 |Array                   |The array of images.    |
+---------------------------+------------------------+------------------------+
|images.\ **status**        |String                  |The image status, like  |
|                           |                        |``ACTIVE``.             |
+---------------------------+------------------------+------------------------+
|images.\ **updated**       |Date                    |The date and time that  |
|                           |                        |the image was last      |
|                           |                        |updated.                |
+---------------------------+------------------------+------------------------+
|images.\ **links**         |String                  |The array of image      |
|                           |                        |links for self and      |
|                           |                        |bookmark.               |
+---------------------------+------------------------+------------------------+
|images.links.\ **href**    |Uuid                    |The URL for the image   |
|                           |                        |and the associated      |
|                           |                        |``rel``.                |
+---------------------------+------------------------+------------------------+
|images.links.\ **rel**     |Uuid                    |The descriptive field   |
|                           |                        |for the associated      |
|                           |                        |``href``, which is      |
|                           |                        |either ``self``,        |
|                           |                        |``bookmark``, or        |
|                           |                        |``alternate``.          |
+---------------------------+------------------------+------------------------+
|images.links.\ **type**    |Uuid                    |The alternate image     |
|                           |                        |type.                   |
+---------------------------+------------------------+------------------------+
|images.\ **OS-             |String                  |The disk configuration  |
|DCF:diskConfig**           |                        |value. Valid values are |
|                           |                        |``AUTO`` and ``MANUAL``.|
+---------------------------+------------------------+------------------------+
|images.\ **id**            |Uuid                    |The image ID.           |
+---------------------------+------------------------+------------------------+
|images.\ **updated**       |Date                    |The date and time that  |
|                           |                        |the image was last      |
|                           |                        |updated.                |
+---------------------------+------------------------+------------------------+
|images.\ **OS-             |String                  |The image size.         |
|EXT-IMG-SIZE:size**        |                        |                        |
+---------------------------+------------------------+------------------------+
|images.\ **name**          |String                  |The image name.         |
|                           |                        |                        |
+---------------------------+------------------------+------------------------+
|images.\ **created**       |Date                    |The date and time that  |
|                           |                        |the image was created.  |
+---------------------------+------------------------+------------------------+
|images.\ **minDisk**       |Int                     |The minimum number of   |
|                           |                        |gigabytes of disk       |
|                           |                        |storage.                |
+---------------------------+------------------------+------------------------+
|images.\ **progress**      |Int                     |The completion          |
|                           |                        |percentage for an       |
|                           |                        |image. ``100``          |
|                           |                        |indicates the image     |
|                           |                        |build is completed.     |
+---------------------------+------------------------+------------------------+
|images.\ **minRam**        |Int                     |The specified minimum   |
|                           |                        |amount of RAM in        |
|                           |                        |megabytes.              |
+---------------------------+------------------------+------------------------+
|images.\ **metadata**      |Array                   |Array of metadata key   |
|                           |                        |pairs containing        |
|                           |                        |information about the   |
|                           |                        |image.                  |
+---------------------------+------------------------+------------------------+


**Example Retrieve list of images with details: JSON response**


The following example shows only a few images in the list for brevity.

.. code::

       Status Code: 200 OK
       Content-Length: 91825
       Content-Type: application/json
       Date: Thu, 09 Jul 2015 16:16:03 GMT, Thu, 09 Jul 2015 16:16:06 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-5e110eed-c310-4e8a-806f-313865f189bd


.. code::

   {
     "images": [
       {
         "status": "ACTIVE",
         "updated": "2015-07-09T16:12:57Z",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/images/28555e09-5639-43f9-b64b-9c98c78520ad",
             "rel": "self"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/820712/images/28555e09-5639-43f9-b64b-9c98c78520ad",
             "rel": "bookmark"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/images/28555e09-5639-43f9-b64b-9c98c78520ad",
             "type": "application/vnd.openstack.image",
             "rel": "alternate"
           }
         ],
         "OS-DCF:diskConfig": "MANUAL",
         "id": "28555e09-5639-43f9-b64b-9c98c78520ad",
         "OS-EXT-IMG-SIZE:size": 198846343,
         "name": "CoreOS (Alpha)",
         "created": "2015-07-09T14:48:20Z",
         "minDisk": 20,
         "progress": 100,
         "minRam": 512,
         "metadata": {
           "os_distro": "com.coreos",
           "os_type": "linux"
         }
       },
       {
         "status": "ACTIVE",
         "updated": "2015-07-09T10:23:14Z",
         "links": [
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/images/8b8c73b6-689d-45d2-a7a4-33aae5e011f1",
             "rel": "self"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/820712/images/8b8c73b6-689d-45d2-a7a4-33aae5e011f1",
             "rel": "bookmark"
           },
           {
             "href": "https://dfw.servers.api.rackspacecloud.com/images/8b8c73b6-689d-45d2-a7a4-33aae5e011f1",
             "type": "application/vnd.openstack.image",
             "rel": "alternate"
           }
         ],
         "OS-DCF:diskConfig": "AUTO",
         "id": "8b8c73b6-689d-45d2-a7a4-33aae5e011f1",
         "OS-EXT-IMG-SIZE:size": 1905244160,
         "name": "Daily-wordpress.voiceoversbycat.com-1436437083",
         "created": "2015-07-09T10:18:04Z",
         "minDisk": 20,
         "server": {
           "id": "8f64d643-f48a-459c-a7af-717dfc7580ee",
           "links": [
             {
               "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/servers/8f64d643-f48a-459c-a7af-717dfc7580ee",
               "rel": "self"
             },
             {
               "href": "https://dfw.servers.api.rackspacecloud.com/820712/servers/8f64d643-f48a-459c-a7af-717dfc7580ee",
               "rel": "bookmark"
             }
           ]
         },
         "progress": 100,
         "minRam": 512,
         "metadata": {
           "os_distro": "ubuntu",
           "os_type": "linux"
         }
       }
     ]
   }




