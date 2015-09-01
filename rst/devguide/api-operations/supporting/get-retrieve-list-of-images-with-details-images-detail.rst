
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

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

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|images                    |Array                    |The array of images.     |
+--------------------------+-------------------------+-------------------------+
|status                    |String                   |The image status, like   |
|                          |                         |``ACTIVE``.              |
+--------------------------+-------------------------+-------------------------+
|updated                   |Date                     |The date and time that   |
|                          |                         |the image was last       |
|                          |                         |updated.                 |
+--------------------------+-------------------------+-------------------------+
|links                     |String                   |The array of image links |
|                          |                         |for self and bookmark.   |
+--------------------------+-------------------------+-------------------------+
|href                      |Uuid                     |The URL for the image    |
|                          |                         |and the associated       |
|                          |                         |``rel``.                 |
+--------------------------+-------------------------+-------------------------+
|rel                       |Uuid                     |The descriptive field    |
|                          |                         |for the associated       |
|                          |                         |``href``, which is       |
|                          |                         |either ``self``,         |
|                          |                         |``bookmark``, or         |
|                          |                         |``alternate``.           |
+--------------------------+-------------------------+-------------------------+
|type                      |Uuid                     |The alternate image type.|
+--------------------------+-------------------------+-------------------------+
|OS-DCF:diskConfig         |String                   |The disk configuration   |
|                          |                         |value. Valid values are  |
|                          |                         |``AUTO`` and ``MANUAL``. |
+--------------------------+-------------------------+-------------------------+
|id                        |Uuid                     |The image ID.            |
+--------------------------+-------------------------+-------------------------+
|updated                   |Date                     |The date and time that   |
|                          |                         |the image was last       |
|                          |                         |updated.                 |
+--------------------------+-------------------------+-------------------------+
|OS-EXT-IMG-SIZE:size      |String                   |The image size.          |
+--------------------------+-------------------------+-------------------------+
|name                      |String                   |The image name.          |
+--------------------------+-------------------------+-------------------------+
|created                   |Date                     |The date and time that   |
|                          |                         |the image was created.   |
+--------------------------+-------------------------+-------------------------+
|minDisk                   |Int                      |The minimum number of    |
|                          |                         |gigabytes of disk        |
|                          |                         |storage.                 |
+--------------------------+-------------------------+-------------------------+
|progress                  |Int                      |The completion           |
|                          |                         |percentage for an image. |
|                          |                         |``100`` indicates the    |
|                          |                         |image build is completed.|
+--------------------------+-------------------------+-------------------------+
|minRam                    |Int                      |The specified minimum    |
|                          |                         |amount of RAM in         |
|                          |                         |megabytes.               |
+--------------------------+-------------------------+-------------------------+
|metadata                  |Array                    |Array of metadata key    |
|                          |                         |pairs containing         |
|                          |                         |information about the    |
|                          |                         |image.                   |
+--------------------------+-------------------------+-------------------------+





**Example Retrieve list of images with details: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 91825
        Content-Type: application/json
        Date: Thu, 09 Jul 2015 16:16:03 GMT, Thu, 09 Jul 2015 16:16:06 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-5e110eed-c310-4e8a-806f-313865f189bd


