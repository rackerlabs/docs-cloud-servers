.. _get-retrieve-list-of-images-images:

Retrieve list of images
-----------------------

.. code::

    GET /images

This operation lists IDs, names, and links for all images visible by the
account.

The optional minDisk and minRam attributes set the minimum disk and RAM
required to create a server with the image.

The image_type field in the response indicates whether the image is built-in
``(base)`` or custom ``(snapshot)``.

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

**Example Retrieve list of images: JSON request**


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
|images.\ **id**            |Uuid                    |The image ID.           |
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
|images.\  **name**         |String                  |The image name.         |
|                           |                        |                        |
+---------------------------+------------------------+------------------------+


**Example Retrieve list of images: JSON response**


The following example shows only a few images in the list for brevity.

.. code::

       Status Code: 200 OK
       Content-Length: 26264
       Content-Type: application/json
       Date: Thu, 09 Jul 2015 15:53:01 GMT, Thu, 09 Jul 2015 15:53:04 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-f0ce0b60-923f-4f02-aafe-090b95231323


.. code::

   {
     "images": [
       {
           "id": "6455fff1-1f0e-46e3-a795-6c88738d7280",
           "links": [
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/images/6455fff1-1f0e-46e3-a795-6c88738d7280",
                   "rel": "self"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/820712/images/6455fff1-1f0e-46e3-a795-6c88738d7280",
                   "rel": "bookmark"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/images/6455fff1-1f0e-46e3-a795-6c88738d7280",
                   "type": "application/vnd.openstack.image",
                   "rel": "alternate"
               }
           ],
           "name": "CentOS 7 (PVHVM)"
       },
       {
           "id": "fa26666f-b71b-492e-8bd9-d29eabc5b49f",
           "links": [
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/images/fa26666f-b71b-492e-8bd9-d29eabc5b49f",
                   "rel": "self"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/820712/images/fa26666f-b71b-492e-8bd9-d29eabc5b49f",
                   "rel": "bookmark"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/images/fa26666f-b71b-492e-8bd9-d29eabc5b49f",
                   "type": "application/vnd.openstack.image",
                   "rel": "alternate"
               }
           ],
           "name": "Ubuntu 15.04 (Vivid Vervet) (PVHVM)"
       },
       {
           "id": "33f0f56f-a9d2-4ffc-843f-94b80860f2c1",
           "links": [
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/images/33f0f56f-a9d2-4ffc-843f-94b80860f2c1",
                   "rel": "self"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/820712/images/33f0f56f-a9d2-4ffc-843f-94b80860f2c1",
                   "rel": "bookmark"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/images/33f0f56f-a9d2-4ffc-843f-94b80860f2c1",
                   "type": "application/vnd.openstack.image",
                   "rel": "alternate"
               }
           ],
           "name": "Gentoo 15.2 (PVHVM)"
       }
     ]
   }




