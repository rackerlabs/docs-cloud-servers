.. _get-retrieve-list-of-rate-and-absolute-limits-limits:

Retrieve list of rate and absolute limits
-----------------------------------------

.. code::

    GET /limits

This operation retrieves the current rate limits and absolute limits for your
account.

Applications can programmatically determine current account limits by using
this API operation.



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

**Example Retrieve list of rate and absolute limits: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------------+---------------------+----------------------+
|Name                            |Type                 |Description           |
+================================+=====================+======================+
|**limits**                      |Object               |The container of      |
|                                |                     |limits attributes.    |
+--------------------------------+---------------------+----------------------+
|limits.\ **absolute**           |Object               |The container of      |
|                                |                     |absolute limits       |
|                                |                     |attributes.           |
+--------------------------------+---------------------+----------------------+
|limits.absolute.\               |Int                  |The maximum amount of |
|**maxTotalRAMSize**             |                     |RAM allowed.          |
+--------------------------------+---------------------+----------------------+
|limits.absolute.\               |Int                  |The total amount of   |
|**totalRAMUsed**                |                     |RAM used.             |
+--------------------------------+---------------------+----------------------+
|limits.absolute.\               |Int                  |The maximum allowed   |
|**maxServerMeta**               |                     |server metadata items.|
+--------------------------------+---------------------+----------------------+
|limits.absolute.\               |Int                  |The maximum allowed   |
|**maxImageMeta**                |                     |image metadata items. |
+--------------------------------+---------------------+----------------------+
|limits.absolute.\               |Int                  |The maximum number of |
|**maxPersonality**              |                     |personality files.    |
+--------------------------------+---------------------+----------------------+
|limits.absolute.\               |Int                  |The size of the       |
|**maxPersonalitySize**          |                     |personality files.    |
+--------------------------------+---------------------+----------------------+
|limits.\ **rate**               |Array                |The array of rate     |
|                                |                     |objects.              |
+--------------------------------+---------------------+----------------------+
|limits.rate.\ **limit**         |Array                |The array of rate     |
|                                |                     |limit objects.        |
+--------------------------------+---------------------+----------------------+
|limits.rate.limit.\             |Date                 |The next available    |
|**next-available**              |                     |rate limit date and   |
|                                |                     |time.                 |
+--------------------------------+---------------------+----------------------+
|limits.rate.limit.\ **verb**    |String               |The HTTP operation.   |
|                                |                     |                      |
+--------------------------------+---------------------+----------------------+
|limits.rate.limit.\  **value**  |String               |The max allowed time  |
|                                |                     |in units.             |
+--------------------------------+---------------------+----------------------+
|limits.rate.limit.\             |Date                 |The time remaining    |
|**remaining**                   |                     |for the rate limit in |
|                                |                     |units.                |
+--------------------------------+---------------------+----------------------+
|limits.rate.limit.\ **unit**    |Date                 |The type of unit for  |
|                                |                     |the rate limit. For   |
|                                |                     |example, ``DAY`` or   |
|                                |                     |``MINUTE``.           |
+--------------------------------+---------------------+----------------------+


**Example Retrieve list of rate and absolute limits: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 3010
       Content-Type: application/json
       Date: Wed, 18 Mar 2015 20:23:18 GMT, Wed, 18 Mar 2015 20:23:19 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-48d05db0-dd97-4aef-87f2-11177ab8c262


.. code::

   {
       "limits": {
           "absolute": {
               "totalSnapshotsUsed": 0,
               "maxTotalVolumeGigabytes": 1000,
               "totalGigabytesUsed": 0,
               "maxTotalSnapshots": 10,
               "totalVolumesUsed": 0,
               "maxTotalVolumes": 10
           },
           "rate": [
               {
                   "limit": [
                       {
                           "next-available": "2012-09-10T20:11:45.146Z",
                           "remaining": 0,
                           "unit": "DAY",
                           "value": 0,
                           "verb": "POST"
                       },
                       {
                           "next-available": "2012-09-10T20:11:45.146Z",
                           "remaining": 0,
                           "unit": "MINUTE",
                           "value": 0,
                           "verb": "GET"
                       }
                   ],
                   "regex": "/v[^/]/(\\d+)/(rax-networks)/?.*",
                   "uri": "/rax-networks"
               }
           ]
       }
   }



