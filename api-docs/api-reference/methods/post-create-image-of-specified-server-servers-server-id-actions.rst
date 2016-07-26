.. _post-create-image-of-specified-server-servers-server-id-actions:

Create image of specified server
--------------------------------

.. code::

    POST /servers/{server_id}/action

This operation creates a new image for a specified server. Once complete, you
can use your new image to rebuild or create servers. The full URL to the newly
created image is returned through the ``Location`` header. You can retrieve
additional attributes for the image including its creation status by issuing a
subsequent ``GET`` on that URL.

Image creation is an asynchronous operation, so coordinating the creation with
data quiescence, and so on, is currently not possible.

.. note::
   This operation is not available for OnMetal servers.

In addition to creating images manually, you may also schedule images of your
server automatically.

Specify the target server ID in the URI.

In the request body, specify the ``createImage`` action, followed by attributes.



This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|202                      |Successful               |Request succeeded.       |
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
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+


This table shows the body parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**createImage**           |Object                  |Specification of the     |
|                          |                        |createImage action for   |
|                          |                        |the specified server.    |
+--------------------------+------------------------+-------------------------+
|createImage.\ **name**    |String                  |The name of the new      |
|                          |                        |image.                   |
+--------------------------+------------------------+-------------------------+
|createImage.\ **metadata**|Object                  |The container of the     |
|                          |                        |metadata for the new     |
|                          |                        |image.                   |
+--------------------------+------------------------+-------------------------+
|createImage.\ **meta**    |Object                  |A metadata keypair,      |
|                          |                        |specifying ImageType or  |
|                          |                        |ImageVersion, for        |
|                          |                        |example.                 |
+--------------------------+------------------------+-------------------------+


**Example Create image of specified server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "createImage" : {
           "name" : "new-image",
           "metadata": {
               "ImageType": "Gold",
               "ImageVersion": "2.0"
           }
       }
   }

Response
^^^^^^^^


**Example Create image of specified server: JSON response**


.. code::

   Status Code: 202 No Content
   Content-Length: 0
   Content-Type: application/json
   Date: Thu, 04 Dec 2014 21:45:47 GMT
   Server: Jetty(8.0.y.z-SNAPSHOT)
   Via: 1.1 Repose (Repose/2.12)
   x-compute-request-id




