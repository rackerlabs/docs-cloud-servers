.. _put-set-image-metadata-item-for-specified-image-images-image-id-metadata-key:

Set image metadata item for specified image
-------------------------------------------

.. code::

    PUT /images/{image_id}/metadata/{key}

This operation sets metadata for an image that you previously created.

If your request includes keys that do not exist, they will be added. If it
includes existing metadata keys, those entries will be changed to match the
keys in the request body.

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

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{image_id}                |Uuid                    |The UUID for the image.  |
+--------------------------+------------------------+-------------------------+
|{key}                     |Uuid                    |The key of the image     |
|                          |                        |metadata item.           |
+--------------------------+------------------------+-------------------------+

This table shows the body parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**meta**                  |Object                  |The container of         |
|                          |                        |metadata for images.     |
|                          |                        |Within this container,   |
|                          |                        |there may be one or more |
|                          |                        |metadata key pairs.      |
+--------------------------+------------------------+-------------------------+

**Example Set image metadata item for specified image: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
     "meta": {
       "label": "Replaced"
     }
   }

Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**meta**                  |Object                  |The container of         |
|                          |                        |metadata for images.     |
|                          |                        |Within this container,   |
|                          |                        |there may be one or more |
|                          |                        |metadata key pairs.      |
+--------------------------+------------------------+-------------------------+


**Example Set image metadata item for specified image: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 31
       Content-Type: application/json
       Date: Wed, 15 Jul 2015 16:46:44 GMT, Wed, 15 Jul 2015 16:46:45 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-7a75bb96-54eb-4847-a73c-4f697f42b175


.. code::

   {
     "meta": {
       "label": "Replaced"
     }
   }


