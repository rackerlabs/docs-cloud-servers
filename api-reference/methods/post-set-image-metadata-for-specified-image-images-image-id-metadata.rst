.. _post-set-image-metadata-for-specified-image-images-image-id-metadata:

Set image metadata for specified image
--------------------------------------

.. code::

    POST /images/{image_id}/metadata

This operation sets metadata for an image that you previously created.

If your request includes keys that do not exist, they will be added. If it
includes existing metadata keys, those entries will be changed to match the
keys in the request body.

Specify the image ID in the URI.

The optional key, ``auto_disk_config``,  determines how a cloud server's root
disk partition is handled when the server is started or resized. It has the
following possible user-selectable values:

-  ``TRUE``:
    The root partition is expanded to encompass all of the available virtual
    disk. This setting results in an OS_DCF:diskConfig value of ``AUTO`` on a
    server built with this image.
-  ``FALSE``:
    The root partition remains the same size as the original image.  Extra
    virtual disk is seen as unformatted free space by the operating system.
    This setting results in an OS_DCF:diskConfig value of ``MANUAL`` on a
    server built with this image.

The non-user-selectable value ``DISABLED`` results in an OS_DCF:diskConfig
value of ``MANUAL`` on a server built with this image.

The auto_disk_config key is related to, and can actually control, the available
:ref:`Disk Configuration Extension<disk-configuration-extension>` attribute:
``OS-DCF:diskConfig``.

.. warning::

	We do not advise changing auto_disk_config during resizes, even when
	allowed, since it can have unintended consequences.


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

**Example Set image metadata for specified image: JSON request**

.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "metadata": {
           "Category": "Webserver Retail Outlet project",
           "Owner": "John, Doe",
           "Label": "Updated"
       }
   }

Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**metadata**              |Object                  |The container of         |
|                          |                        |metadata for images.     |
+--------------------------+------------------------+-------------------------+


**Example Set image metadata for specified image: JSON response**

.. code::

       Status Code: 200 OK
       Content-Length: 870
       Content-Type: application/json
       Date: Wed, 15 Jul 2015 16:21:10 GMT, Wed, 15 Jul 2015 16:21:11 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-a7b3db00-0692-473d-93d3-e330eabc58b1


.. code::

   {
     "metadata": {
       "com.rackspace__1__options": "0",
       "owner": "John, Doe",
       "base_image_ref": "ffa476b1-9b14-46bd-99a8-862d1d94eb7a",
       "category": "Webserver-Beta Retail Outlet project",
       "os_distro": "ubuntu",
       "label": "Updated",
       "auto_disk_config": "True",
       "os_type": "linux"
     }
   }


