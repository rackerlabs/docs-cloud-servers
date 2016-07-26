.. _get-show-scheduled-images-servers-server-id-rax-si-scheduled-image:

Show scheduled Images
---------------------

.. code::

    GET /servers/{server_id}/rax-si-image-schedule

This operation shows scheduled images for the specified server.

This operation returns the retention value if the server has scheduled images
enabled. For weekly images, the response also includes the scheduled day of the
week for the image. If the server has scheduled images disabled, an
``HTTP 404`` is returned.

In the URI, specify the server ID.


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
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+

This operation does not accept a request body.


**Example Show scheduled Images: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


Response
^^^^^^^^


This table shows the body parameters for the response:

+-----------------------------+-----------------------+-----------------------+
|Name                         |Type                   |Description            |
+=============================+=======================+=======================+
|**image_schedule**           |Object *(Required)*    |The container for the  |
|                             |                       |image schedule.        |
+-----------------------------+-----------------------+-----------------------+
|image_schedule.\             |Int *(Required)*       |The number of days     |
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


**Example Show scheduled images (daily - success): JSON response**


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

**Example Show scheduled images (weekly - success): JSON response**


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


**Example Show scheduled images (not found): JSON response**


.. code::

       Status Code: 404 Not Found
       Content-Length: 123
       Content-Type: application/json; charset=UTF-8
       Date: Thu, 29 Jan 2015 22:24:11 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-e20a9646-e225-403b-9e81-53c22728cbaf


.. code::

   {
     "itemNotFound": {
       "message": "Image schedule does not exist for server 4a24d643-f48a-459c-a7af-939dfc7580ee",
       "code": 404
     }
   }




