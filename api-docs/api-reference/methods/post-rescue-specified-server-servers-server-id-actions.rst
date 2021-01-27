.. _post-rescue-specified-server-servers-server-id-actions:

Rescue specified server
-----------------------

.. code::

    POST /servers/{server_id}/action

This operation puts a server into rescue mode.

You might enter rescue mode to reboot a virtual machine (VM) in rescue mode so
that you can access the VM with a new root password and fix any file system and
configuration errors.

Or you might enter rescue mode to debug system issues that prevent you from
booting a server to a usable state.

When you place a server in rescue mode, the following events occur:



#. The VM is shut down.
#. A new VM is created with the following images attached:

   **Primary image** Cleanly running VM based on the image from which the
   original server was created, with a random password. This password is
   returned to you in a response to issuing the rescue mode API call. Use this
   clean image to boot the server and fix any problems.

   **Secondary disk** Image of the VM that needs to be rescued.


When you put a server into rescue mode, you cannot use it until its status goes
from ``ACTIVE`` to ``RESCUE``. This does not happen immediately.

For a full list of possible server status values, see
:ref:`Server Status <server-statuses>`.

.. note::
   The SSH server key will be different on the rescue image than on the
   original server.


Specify the target server ID in the URI.

After you resolve any problems and reboot the rescued server, you can unrescue
the server. The unrescue operation restores the repaired image to running state
with its original password.

In the request body, specify the ``rescue`` action.

.. note::
   If you use ``{"rescue": "none"}`` in the request body, the API will attempt
   to build the rescue mode server from whatever the image_base_image_ref field
   is set to in Nova DB (the original image used to build the server, normally).

   If, instead, you use ``{"rescue": {"rescue_image_ref": " < imageID > "}}``,
   the API uses the specified image for the rescue mode instance. This is
   extremely useful if the image originally used to build the server is now
   either non-functional or has been deleted.

The following extension provides additional rescue with image functionality.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|202                      |Success                  |Request succeeded.       |
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
| **rescue**               |Object                  |Specification of the     |
|                          |                        |rescue action for the    |
|                          |                        |specified server.        |
+--------------------------+------------------------+-------------------------+

**Example Rescue specified server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "rescue" : "none"
   }

**Example Rescue specified server with image: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "rescue" :
           {
               "rescue_image_ref": "c11e2d37-bd93-44f0-b17e-bb87d1022975"
           }
   }

Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
| **adminPass**            |Object                  |The new adminstrator     |
|                          |                        |password.                |
+--------------------------+------------------------+-------------------------+

**Example Rescue specified server (same for both requests): JSON request**


.. code::

       Status Code: 202 OK
       Content-Length: 1250
       Content-Type: application/json
       Date: Thu, 10 Dec 2014 19:43:18 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-8c905dfe-2c9a-17e5-8e53-4478e2813c75


.. code::

   {
     "adminPass": "m7UKdGiKFpqM"
   }




