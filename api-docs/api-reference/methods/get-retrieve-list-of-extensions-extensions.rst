.. _get-retrieve-list-of-extensions-extensions:

Retrieve list of extensions
---------------------------

.. code::

    GET /extensions

This operation retrieves the list of available extensions.

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

This operation does not accept a request body.

**Example Retrieve list of extensions: JSON request**


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
|**extensions**            |Array                   |The array of extensions. |
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|extensions.\ **updated**  |Date                    |The most recent update   |
|                          |                        |date for the extension.  |
+--------------------------+------------------------+-------------------------+
|extensions.\ **name**     |String                  |The name of the          |
|                          |                        |extension.               |
+--------------------------+------------------------+-------------------------+
|extensions.\ **links**    |Array                   |The array of links for   |
|                          |                        |the extension.           |
+--------------------------+------------------------+-------------------------+
|extensions.\ **namespace**|String                  |The namespace of the     |
|                          |                        |extension.               |
+--------------------------+------------------------+-------------------------+
|extensions.\ **alias**    |String                  |The alias, or short      |
|                          |                        |name, of the extension.  |
+--------------------------+------------------------+-------------------------+
|extensions.\              |String                  |The description of the   |
|**description**           |                        |extension.               |
+--------------------------+------------------------+-------------------------+


**Example Retrieve list of extensions: JSON response**


The following example shows only a few extensions in the list for brevity.

.. code::

       Status Code: 200 OK
       Content-Length: 6045
       Content-Type: application/json
       Date: Fri, 10 Jul 2015 19:53:39 GMT, Fri, 10 Jul 2015 19:53:39 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-79e5a4fe-81ca-4965-b616-6935bab482b3


.. code::

   {
     "extensions": [
       {
         "updated": "2011-09-27T00:00:00Z",
         "name": "DiskConfig",
         "links": [],
         "namespace": "http://docs.openstack.org/compute/ext/disk_config/api/v1.1",
         "alias": "OS-DCF",
         "description": "Disk Management Extension."
       },
       {
         "updated": "2012-03-07T14:46:43Z",
         "name": "OSNetworksV2",
         "links": [],
         "namespace": "http://docs.openstack.org/ext/services/api/v1.1",
         "alias": "os-networksv2",
         "description": "Admin-only Network Management Extension."
       },
       {
         "updated": "2011-08-17T00:00:00Z",
         "name": "VirtualInterfaces",
         "links": [],
         "namespace": "http://docs.openstack.org/compute/ext/virtual_interfacesv2/api/v1.1",
         "alias": "os-virtual-interfacesv2",
         "description": "Virtual interface support."
       },
       {
         "updated": "2013-03-20T00:00:00Z",
         "name": "ScheduledImages",
         "links": [],
         "namespace": "http://docs.openstack.org/servers/api/ext/scheduled_images/v1.0",
         "alias": "rax-si-image-schedule",
         "description": "Enables automatic scheduled images to be taken of a server."
       }
     ]
   }




