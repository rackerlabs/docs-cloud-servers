.. _get-retrieve-log-details-for-a-specified-server-action-servers-server-id-os-instance-actions-request-id:

Retrieve log details for a specified server action
--------------------------------------------------

.. code::

    GET /servers/{server_id}/os-instance-actions/{request-id}

This operation retrieves the log details for a specified server action.



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
|{request_id}              |Uuid                    |The server action        |
|                          |                        |request id.              |
+--------------------------+------------------------+-------------------------+

This operation does not accept a request body.

**Example Retrieve log details for a specified server action: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json

Response
^^^^^^^^

This table shows the body parameters for the response:

+-------------------------------------+-------------------+-------------------+
|Name                                 |Type               |Description        |
+=====================================+===================+===================+
|**instanceAction**                   |Object             |An container of    |
|                                     |                   |instance action    |
|                                     |                   |log entry data for |
|                                     |                   |a specific server  |
|                                     |                   |and action.        |
+-------------------------------------+-------------------+-------------------+
|instanceAction.\ **action**          |String             |The type of action |
|                                     |                   |taken.             |
+-------------------------------------+-------------------+-------------------+
|instanceAction.\ **instance_uuid**   |Uuid               |The server UUID    |
|                                     |                   |where the action   |
|                                     |                   |took place.        |
+-------------------------------------+-------------------+-------------------+
|instanceAction.\ **message**         |Uuid               |The action log     |
|                                     |                   |message, if any.   |
+-------------------------------------+-------------------+-------------------+
|instanceAction.\ **project_id**      |Uuid               |The project id.    |
|                                     |                   |                   |
+-------------------------------------+-------------------+-------------------+
|instanceAction.\ **request_id**      |Uuid               |The action request |
|                                     |                   |id.                |
+-------------------------------------+-------------------+-------------------+
|instanceAction.request_id            |Datetime           |The date and time  |
|                                     |                   |that the actin     |
|                                     |                   |began.             |
+-------------------------------------+-------------------+-------------------+
|instanceAction.\ **user_id**         |String             |The id of the user |
|                                     |                   |who requested the  |
|                                     |                   |action.            |
+-------------------------------------+-------------------+-------------------+


**Example Retrieve log details for a specified server action: JSON response**


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




