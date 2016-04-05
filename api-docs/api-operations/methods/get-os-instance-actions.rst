.. _list-instance-actions:

List OS Instance Actions 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /servers/{server_id}/os-instance-actions
    
This operation returns a list of available actions on the specified server.

Specify the target server ID in the URI.


This table shows the possible response codes for this operation:

+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Successful               |Request succeeded.       |
+--------------------------+-------------------------+-------------------------+
|400                       |Error                    |A general error has      |
|                          |                         |occured.                 |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |Unauthorized.            |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Forbidden.               |
+--------------------------+-------------------------+-------------------------+
|404                       |Not Found                |Not Found.               |
+--------------------------+-------------------------+-------------------------+
|405                       |Bad Method               |Bad method.              |
+--------------------------+-------------------------+-------------------------+
|413                       |Over Limit               |The number of items      |
|                          |                         |returned is above the    |
|                          |                         |allowed limit.           |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+

This operation does not accept a request body.

 
**List Server Actions: Response**

.. code::  

    {
       "instanceActions": [
           {
               "action": "reboot",
               "instance_uuid": "86cf2416-aaa7-4579-a4d7-0bfe42bfa8ff",
               "message": null,
               "project_id": "453265",
               "request_id": "req-7b6f6a5e-daf7-483e-aea5-a11993d1d357",
               "start_time": "2013-08-15T21:40:42.000000",
               "user_id": "35746"
           },
           {
               "action": "create",
               "instance_uuid": "86cf2416-aaa7-4579-a4d7-0bfe42bfa8ff",
               "message": null,
               "project_id": "453265",
               "request_id": "req-920c6627-c8c9-4d02-9d3d-81917e5586df",
               "start_time": "2013-07-12T21:35:37.000000",
               "user_id": "35746"
           }
       ]
    }
