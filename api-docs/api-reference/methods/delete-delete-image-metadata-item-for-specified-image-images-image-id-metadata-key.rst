.. _delete-delete-image-metadata-item-for-specified-image-images-image-id-metadata-key:

Delete image metadata item for specified image
----------------------------------------------

.. code::

    DELETE /images/{image_id}/metadata/{key}

This operation deletes a metadata for an image.

Specify the image ID and metadata key in the URI.

This table shows the possible response codes for this operation:

+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|204                      |Success                  |No Content.              |
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

+-------------------------+-------------------------+-------------------------+
|Name                     |Type                     |Description              |
+=========================+=========================+=========================+
|{image_id}               |Uuid                     |The UUID for the image.  |
+-------------------------+-------------------------+-------------------------+
|{key}                    |Uuid                     |The key of the image     |
|                         |                         |metadata item.           |
+-------------------------+-------------------------+-------------------------+


This operation does not accept a request body.

**Example Delete image metadata item for specified image: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json

Response
^^^^^^^^

**Example Delete image metadata item for specified image: JSON response**


.. code::

       HTTP/1.1 204 No Content
       Date: Wed, 15 Jul 2015 17:05:13 GMT
       Via: 1.1 Repose (Repose/6.2.1.2)
       Date: Wed, 15 Jul 2015 17:05:13 GMT
       Content-Type: application/json
       X-Compute-Request-Id: req-b34ee94e-1760-4f75-8073-978f75d68c3d
       Server: Jetty(9.2.z-SNAPSHOT)




