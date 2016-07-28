.. _get-retrieve-quotas-os-quota-sets-tenant-id:

Retrieve quotas
---------------

.. code::

    GET /os-quota-sets/{tenant_id}

This operation shows current quotas for a tenant.

In the URI, specify the tenant ID.



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
|{tenant_id}               |String                  |The tenant id.           |
+--------------------------+------------------------+-------------------------+

This operation does not accept a request body.

**Example Retrieve quotas: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json

Response
^^^^^^^^

This table shows the body parameters for the response:

+---------------------------+------------------------+------------------------+
|Name                       |Type                    |Description             |
+===========================+========================+========================+
|**quota-set**              |Object                  |The container of quota- |
|                           |                        |sets.                   |
+---------------------------+------------------------+------------------------+
|quota-set.\ **ram**        |Int                     |The quota for ram.      |
|                           |                        |                        |
+---------------------------+------------------------+------------------------+
|quota-set.\ **instances**  |Uuid                    |The quota for instances.|
|                           |                        |                        |
+---------------------------+------------------------+------------------------+
|quota-set.\                |Uuid                    |The quota for metadata- |
|**metadata-items**         |                        |items.                  |
+---------------------------+------------------------+------------------------+


**Example Retrieve quotas: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 513
       Content-Type: application/json
       Date: Fri, 10 Jul 2015 17:33:12 GMT, Fri, 10 Jul 2015 17:33:12 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-01fb912a-5a59-4ac1-80d6-368c2a2e0df8


.. code::

   {
     "quota_set": {
       "injected_file_content_bytes": 1000,
       "metadata_items": 40,
       "ram": 131072,
       "security_group_rules": -1,
       "onmetal-memory-v1-ram": 131072,
       "onmetal-compute-v1-instances": 100,
       "onmetal-compute-v1-ram": 131072,
       "networks": 10,
       "floating_ips": -1,
       "key_pairs": 100,
       "id": "1234567",
       "instances": 100,
       "onmetal-memory-v1-instances": 100,
       "injected_files": 5,
       "onmetal-io-v1-instances": 100,
       "cores": -1,
       "onmetal-io-v1-ram": 131072,
       "fixed_ips": -1,
       "injected_file_path_bytes": 255,
       "security_groups": -1
     }
   }




