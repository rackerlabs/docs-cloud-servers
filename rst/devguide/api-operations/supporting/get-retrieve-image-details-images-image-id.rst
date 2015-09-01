
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve image details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /images/{image_id}

Retrieves details of a specified image.

Specify the image ID in the URI.

This operation returns details of the specified image in the response body. The image_type field in the 				response indicates whether the image is built-in ``(base)`` or custom ``(snapshot)``.

.. note::
 The response body does not include the serverId field. To retrieve the serverId field, get 						details for all images. 
 
 





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
|{image_id}                |Uuid                     |The UUID for the image.  |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Retrieve image details: JSON request**


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
|image                     |Object                   |The container of image   |
|                          |                         |details.                 |
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
|server                    |Object                   |The container of server  |
|                          |                         |attributes for the image.|
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





**Example Retrieve image details: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 2230
        Content-Type: application/json
        Date: Thu, 09 Jul 2015 18:24:01 GMT, Thu, 09 Jul 2015 18:24:02 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-5ba3fae8-5daf-48c7-9be1-6de842e50ca9


