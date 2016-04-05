.. _get-instance-action-details:

Show OS Instance Action details 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /servers/{server_id}/os-instance-actions/{request-id}
    
This operation returns the details of the specified action on the specified server.

Specify the target server ID and request ID in the URI.
    
This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Successful               |Request succeeded.       |
+--------------------------+-------------------------+-------------------------+
|400                       |BadRequest               |A general error has      |
|                          |                         |occured.                 |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |Unauthorized.            |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Forbidden.               |
+--------------------------+-------------------------+-------------------------+
|404                       |Not Found                |Not found.               |
+--------------------------+-------------------------+-------------------------+

This operation does not accept a request body.

 
**Show Server Action (External) Response**

.. code::  

    {
       "instanceAction": {
           "action": "create",
           "instance_uuid": "86cf2416-aaa7-4579-a4d7-0bfe42bfa8ff",
           "message": null,
           "project_id": "453265",
           "request_id": "req-920c6627-c8c9-4d02-9d3d-81917e5586df",
           "start_time": "2013-07-12T21:35:37.000000",
           "user_id": "35746"
       }
    }

 
**Show Server Action (Internal) Response**

.. code::  

    {
       "instanceAction": {
           "action": "create",
           "events": [
               {
                   "event": "compute_run_instance",
                   "finish_time": "2013-07-12T21:45:44.000000",
                   "result": "Success",
                   "start_time": "2013-07-12T21:35:42.000000",
                   "traceback": null
               },
               {
                   "event": "schedule",
                   "finish_time": "2013-07-12T21:35:42.000000",
                   "result": "Success",
                   "start_time": "2013-07-12T21:35:38.000000",
                   "traceback": null
               }
           ],
           "instance_uuid": "86cf2416-aaa7-4579-a4d7-0bfe42bfa8ff",
           "message": null,
           "project_id": "453265",
           "request_id": "req-920c6627-c8c9-4d02-9d3d-81917e5586df",
           "start_time": "2013-07-12T21:35:37.000000",
           "user_id": "35746"
       }
    }
