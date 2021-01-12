.. _post-enable-scheduled-images-servers-server-id-rax-si-scheduled-image:

Enable scheduled Images
-----------------------

.. code::

    POST /servers/{server_id}/rax-si-image-schedule

This operation enables scheduled images on a server, by creating a
``image_schedule`` resource. When your images are created, they are named
according to one of the following schemes:

* ``daily-{server-name}-{10-digit-number}``
* ``weekly-{server-name}-{10-digit-number}``

Image names are limited to 255 characters. The ``{server-name}`` may be
truncated, if necessary, for the scheduled snapshot image name to meet this
limit.

If you want to change from daily to weekly scheduled images, simply post a new
request containing the day of week and the retention value you desire.
Likewise, if you want to switch from weekly to daily scheduled images, simply
post a new request containing only a retention value.

In the URI, specify the server ID.

In the request body, for both daily and weekly requests, specify ``retention``
specifies the number of scheduled images created by the scheduled images
service to keep for a server. The retention value must be a positive integer
from 1 to 65,535 (the system limit).

In the request body, for weekly requests, specify ``day_of_week``, which
indicates the day for image creation.

.. note::

   Regarding Retention:

   - Excess scheduled image removal will be done at the time the scheduled
     images service successfully adds a new snapshot to your account.
   - The way the scheduled images service recognizes that an image is eligible
     for removal is by locating the following user metadata on the image:
     ``org.openstack__1__created-by: scheduled-images-service``. To save a
     scheduled image so that it is not eligible for retention culling, simply
     remove this metadata element. We do not recommend adding the above
     metadata element to an image manually.
   - If a retention value has already been specified for a server, it is
     overridden.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200                      |Success                  |Request succeeded.       |
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
|{server_id}              |Uuid                     |The UUID for the server. |
+-------------------------+-------------------------+-------------------------+


This table shows the body parameters for the request:

+-----------------------------+-----------------------+-----------------------+
|Name                         |Type                   |Description            |
+=============================+=======================+=======================+
|**image_schedule**           |Object                 |The container for the  |
|                             |                       |image schedule.        |
+-----------------------------+-----------------------+-----------------------+
|image_schedule.\             |Int                    |The number of days     |
|**retention**                |                       |that an Image should   |
|                             |                       |be retained.           |
+-----------------------------+-----------------------+-----------------------+
|image_schedule.\             |String *(Optional)*    |The chosen day of the  |
|**day_of_week**              |                       |week for the image     |
|                             |                       |creation. The allowed  |
|                             |                       |values for this field  |
|                             |                       |are: ``SUNDAY``,       |
|                             |                       |``MONDAY``,            |
|                             |                       |``TUESDAY``,           |
|                             |                       |``WEDNESDAY``,         |
|                             |                       |``THURSDAY``,          |
|                             |                       |``FRIDAY``, and        |
|                             |                       |``SATURDAY``.          |
+-----------------------------+-----------------------+-----------------------+

**Example Enable scheduled images (daily): JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "image_schedule" : {
            "retention": 7
       }
   }


**Example Enable scheduled images (weekly): JSON request**


.. code::

   {
        "image_schedule": {
              "retention": 5,
              "day_of_week": "SATURDAY"
        }
   }

Response
^^^^^^^^

This table shows the body parameters for the response:

+-----------------------------+-----------------------+-----------------------+
|Name                         |Type                   |Description            |
+=============================+=======================+=======================+
|**image_schedule**           |Object                 |The container for the  |
|                             |                       |image schedule.        |
+-----------------------------+-----------------------+-----------------------+
|image_schedule.\             |Int                    |The number of days     |
|**retention**                |                       |that an Image should   |
|                             |                       |be retained.           |
+-----------------------------+-----------------------+-----------------------+
|image_schedule.\             |String                 |The chosen day of the  |
|**day_of_week**              |                       |week for the image     |
|                             |                       |creation. The allowed  |
|                             |                       |values for this field  |
|                             |                       |are: ``SUNDAY``,       |
|                             |                       |``MONDAY``,            |
|                             |                       |``TUESDAY``,           |
|                             |                       |``WEDNESDAY``,         |
|                             |                       |``THURSDAY``,          |
|                             |                       |``FRIDAY``, and        |
|                             |                       |``SATURDAY``.          |
+-----------------------------+-----------------------+-----------------------+


**Example Enable scheduled images (daily): JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 36
       Content-Type: application/json
       Date: Thu, 29 Jan 2015 22:53:45 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-5d33237d-0f96-4d13-a057-5ab2b1b46f71


.. code::

   {
     "image_schedule": {
       "retention": 7
     }
   }


**Example Enable scheduled images (weekly): JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 63
       Content-Type: application/json
       Date: Thu, 29 Jan 2015 18:25:01 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-f90ae0d1-e0d8-407b-9af0-f4ed79935991


.. code::

   {
     "image_schedule": {
       "day_of_week": "SATURDAY",
       "retention": 5
     }
   }

