
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-retrieve-list-of-images-with-details-images-detail:

Retrieve list of images with details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /images/detail

Retrieves all details for all available images.

This operation returns details of all images in the response body.



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
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""






This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|server                    |Object *(Optional)*      |Filters the list of      |
|                          |                         |images by server.        |
|                          |                         |Specify the server       |
|                          |                         |reference by ID or by    |
|                          |                         |full URL.                |
+--------------------------+-------------------------+-------------------------+
|name                      |String *(Optional)*      |Filters the list of      |
|                          |                         |images by image name.    |
+--------------------------+-------------------------+-------------------------+
|status                    |Imagestatus *(Optional)* |Filters the list of      |
|                          |                         |images by status. In-    |
|                          |                         |flight images have a     |
|                          |                         |status of SAVING and the |
|                          |                         |conditional progress     |
|                          |                         |element contains a value |
|                          |                         |from 0 to 100, which     |
|                          |                         |indicates the percentage |
|                          |                         |completion. Other        |
|                          |                         |possible values for the  |
|                          |                         |status attribute include |
|                          |                         |ACTIVE, DELETED, ERROR,  |
|                          |                         |SAVING, and UNKNOWN.     |
|                          |                         |Images with an ACTIVE    |
|                          |                         |status are available for |
|                          |                         |use.                     |
+--------------------------+-------------------------+-------------------------+
|changes-since             |Datetime *(Optional)*    |Filters the list of      |
|                          |                         |images to those that     |
|                          |                         |have changed since the   |
|                          |                         |changes-since time.      |
+--------------------------+-------------------------+-------------------------+
|marker                    |Uuid *(Optional)*        |The ID of the last item  |
|                          |                         |in the previous list.    |
+--------------------------+-------------------------+-------------------------+
|limit                     |Int *(Optional)*         |Sets the page size.      |
+--------------------------+-------------------------+-------------------------+
|type                      |String *(Optional)*      |Filters Rackspace base   |
|                          |                         |images or any custom     |
|                          |                         |server images that you   |
|                          |                         |have created.            |
+--------------------------+-------------------------+-------------------------+




This operation does not accept a request body.




**Example Retrieve list of images with details: JSON request**


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
|parameters.\ **images**    |Array                    |The array of images.    |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |String                   |The image status, like  |
|**status**                 |                         |``ACTIVE``.             |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |Date                     |The date and time that  |
|**updated**                |                         |the image was last      |
|                           |                         |updated.                |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |String                   |The array of image      |
|**links**                  |                         |links for self and      |
|                           |                         |bookmark.               |
+---------------------------+-------------------------+------------------------+
|parameters.images.links.\  |Uuid                     |The URL for the image   |
|**href**                   |                         |and the associated      |
|                           |                         |``rel``.                |
+---------------------------+-------------------------+------------------------+
|parameters.images.links.\  |Uuid                     |The descriptive field   |
|**rel**                    |                         |for the associated      |
|                           |                         |``href``, which is      |
|                           |                         |either ``self``,        |
|                           |                         |``bookmark``, or        |
|                           |                         |``alternate``.          |
+---------------------------+-------------------------+------------------------+
|parameters.images.links.\  |Uuid                     |The alternate image     |
|**type**                   |                         |type.                   |
+---------------------------+-------------------------+------------------------+
|parameters.images.\ **OS-  |String                   |The disk configuration  |
|DCF:diskConfig**           |                         |value. Valid values are |
|                           |                         |``AUTO`` and ``MANUAL``.|
+---------------------------+-------------------------+------------------------+
|parameters.images.ID       |Uuid                     |The image ID.           |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |Date                     |The date and time that  |
|**updated**                |                         |the image was last      |
|                           |                         |updated.                |
+---------------------------+-------------------------+------------------------+
|parameters.images.\ **OS-  |String                   |The image size.         |
|EXT-IMG-SIZE:size**        |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |String                   |The image name.         |
|**name**                   |                         |                        |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |Date                     |The date and time that  |
|**created**                |                         |the image was created.  |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |Int                      |The minimum number of   |
|**minDisk**                |                         |gigabytes of disk       |
|                           |                         |storage.                |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |Int                      |The completion          |
|**progress**               |                         |percentage for an       |
|                           |                         |image. ``100``          |
|                           |                         |indicates the image     |
|                           |                         |build is completed.     |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |Int                      |The specified minimum   |
|**minRam**                 |                         |amount of RAM in        |
|                           |                         |megabytes.              |
+---------------------------+-------------------------+------------------------+
|parameters.images.\        |Array                    |Array of metadata key   |
|**metadata**               |                         |pairs containing        |
|                           |                         |information about the   |
|                           |                         |image.                  |
+---------------------------+-------------------------+------------------------+







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




