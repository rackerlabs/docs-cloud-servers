.. _get-retrieve-details-for-the-specified-extension-extensions-alias:

Retrieve details for the specified extension
--------------------------------------------

.. code::

    GET /extensions/{alias}

This operation retrieves a specified extension's details.

An unavailable extension issues an ``itemNotFound (404)`` response.

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
|{alias}                  |Uuid                     |The alias, which is a    |
|                         |                         |name for a pointer to a  |
|                         |                         |resource. For example, a |
|                         |                         |named extension.         |
+-------------------------+-------------------------+-------------------------+

This operation does not accept a request body.

**Example Retrieve details for the specified extension: JSON request**


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
|**extension**             |Object                  |The container of         |
|                          |                        |extensions attributes.   |
+--------------------------+------------------------+-------------------------+
|extension.\ **updated**   |Date                    |The most recent update   |
|                          |                        |date for the extension.  |
+--------------------------+------------------------+-------------------------+
|extension.\ **name**      |String                  |The name of the          |
|                          |                        |extension.               |
+--------------------------+------------------------+-------------------------+
|extension.\ **links**     |Array                   |The array of links for   |
|                          |                        |the extension.           |
+--------------------------+------------------------+-------------------------+
|extension.\ **namespace** |String                  |The namespace of the     |
|                          |                        |extension.               |
+--------------------------+------------------------+-------------------------+
|extension.\ **alias**     |String                  |The alias, or short      |
|                          |                        |name, of the extension.  |
+--------------------------+------------------------+-------------------------+
|extension.\               |String                  |The description of the   |
|**description**           |                        |extension.               |
+--------------------------+------------------------+-------------------------+


**Example Retrieve details for the specified extension: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 257
       Content-Type: application/json
       Date: Fri, 10 Jul 2015 19:56:53 GMT, Fri, 10 Jul 2015 19:56:54 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-d612f98f-d446-493c-a1ba-6869828f8a80


.. code::

   {
     "extension": {
       "updated": "2011-08-17T00:00:00Z",
       "name": "VirtualInterfaces",
       "links": [],
       "namespace": "http://docs.openstack.org/compute/ext/virtual_interfacesv2/api/v1.1",
       "alias": "os-virtual-interfacesv2",
       "description": "Virtual interface support."
     }
   }




