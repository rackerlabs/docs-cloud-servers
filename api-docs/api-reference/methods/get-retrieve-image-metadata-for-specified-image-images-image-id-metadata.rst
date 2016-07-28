.. _get-retrieve-image-metadata-for-specified-image-images-image-id-metadata:

Retrieve image metadata for specified image
-------------------------------------------

.. code::

    GET /images/{image_id}/metadata

This operation shows all metadata for an image.

Specify the image ID in the URI.

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

This operation does not accept a request body.

**Example Retrieve image metadata for specified image: JSON request**

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
|**metadata**              |Object                  |The container of         |
|                          |                        |metadata for images.     |
+--------------------------+------------------------+-------------------------+


**Example Retrieve image metadata for specified image: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 1192
       Content-Type: application/json
       Date: Fri, 10 Jul 2015 21:05:50 GMT, Fri, 10 Jul 2015 21:05:51 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-5a2edb56-aa6d-47fc-8124-2cba94d1c7a7


.. code::

   {
     "metadata": {
       "com.rackspace__1__options": "4",
       "instance_type_name": "1GB Standard Instance",
       "com.rackspace__1__release_version": "3",
       "instance_type_vcpus": "1",
       "com.rackspace__1__release_id": "2100",
       "com.rackspace__1__build_core": "1",
       "base_image_ref": "d47aeca3-38d6-4dcb-bccf-534492986ae0",
       "org.openstack__1__os_distro": "com.microsoft.server",
       "image_type": "snapshot",
       "org.openstack__1__os_version": "2008.2",
       "instance_type_ephemeral_gb": "0",
       "com.rackspace__1__build_managed": "1",
       "org.openstack__1__architecture": "x64",
       "com.rackspace__1__visible_core": "1",
       "instance_type_vcpu_weight": "12",
       "instance_type_root_gb": "40",
       "instance_type_id": "3",
       "com.rackspace__1__release_build_date": "2013-04-16",
       "instance_type_rxtx_factor": "3",
       "auto_disk_config": "False",
       "user_id": "346289",
       "com.rackspace__1__visible_managed": "1",
       "instance_uuid": "f879f81a-5455-4e57-a0aa-3773e21c2259",
       "instance_type_memory_mb": "1024",
       "instance_type_swap": "1024",
       "com.rackspace__1__build_rackconnect": "1",
       "instance_type_flavorid": "3",
       "com.rackspace__1__visible_rackconnect": "1",
       "os_type": "windows",
       "rax_activation_profile": "windows",
       "com.rackspace__1__source": "kickstart"
     }
   }




