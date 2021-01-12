.. _get-retrieve-image-metadata-item-for-specified-image-images-image-id-metadata-key:

Retrieve image metadata item for specified image
------------------------------------------------

.. code::

    GET /images/{image_id}/metadata/{key}

This operation shows a metadata item for an image.

Specify the image ID and metadata key in the URI.

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

+-------------------------+-------------------------+-------------------------+
|Name                     |Type                     |Description              |
+=========================+=========================+=========================+
|{image_id}               |Uuid                     |The UUID for the image.  |
+-------------------------+-------------------------+-------------------------+
|{key}                    |Uuid                     |The key of the image     |
|                         |                         |metadata item.           |
+-------------------------+-------------------------+-------------------------+

This operation does not accept a request body.


**Example Retrieve image metadata item for specified image: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json



Response
^^^^^^^^


This table shows the body parameters for the response:

+-------------------------+-------------------------+-------------------------+
|Name                     |Type                     |Description              |
+=========================+=========================+=========================+
|**meta**                 |Object                   |The container of         |
|                         |                         |metadata for images.     |
|                         |                         |Within this container,   |
|                         |                         |there may be one or more |
|                         |                         |metadata key pairs.      |
+-------------------------+-------------------------+-------------------------+



**Example Retrieve image metadata item for specified image: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 30
       Content-Type: application/json
       Date: Wed, 15 Jul 2015 16:41:34 GMT, Wed, 15 Jul 2015 16:41:35 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-b2fd2096-9050-48b8-89d4-a95f37f6c07d


.. code::

   {
     "meta": {
       "label": "Updated"
     }
   }




