.. _post-confirm-server-resize-for-specified-server-servers-server-id-actions:

Confirm server resize for specified server
------------------------------------------

.. code::

    POST /servers/{server_id}/action

This operation confirms the server resize for the specified server.

During a resize operation, the original server is saved for a period of time to
allow roll back if a problem occurs. After you verify that the newly resized
server works properly, use this operation to confirm the resize. After you
confirm the resize, the original server is removed, and you cannot roll back to
that server. All resizes are automatically confirmed after 24 hours, if you do
not explicitly confirm, or revert, the resize.

.. note::
   This operation is not available for OnMetal servers.

Specify the target server ID in the URI.

In the request body, specify the ``confirmResize`` action.

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
|**confirmResize**         |Object                  |Specification of the     |
|                          |                        |confirmResize action for |
|                          |                        |the specified server.    |
+--------------------------+------------------------+-------------------------+


**Example Confirm server resize for specified server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "confirmResize" : null
   }

Response
^^^^^^^^

**Example Confirm server resize for specified server: JSON response**


.. code::

   Status Code: 202 No Content
   Content-Length: 0
   Content-Type: application/json
   Date: Thu, 04 Dec 2014 21:45:47 GMT
   Server: Jetty(8.0.y.z-SNAPSHOT)
   Via: 1.1 Repose (Repose/2.12)
   x-compute-request-id


