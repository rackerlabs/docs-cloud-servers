.. _get-retrieve-list-of-limits-including-used-limits-limits:

Retrieve list of limits including used limits
---------------------------------------------

.. code::

    GET /limits

This operation retrieves the current rate limits and absolute limits for your
account including used limits.

This extension expands the limits operation to show the project usage,
including RAM and instance quotas usage.

In the following example, the ``totalRAMUsed`` value is an extended attribute.


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

**Example Retrieve list of limits including used limits: JSON request**


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
|limits.rate.limit.\ **value**   |String               |The max allowed time  |
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


**Example Retrieve list of limits including used limits: JSON response**


.. code::

   {
     "limits": {
        "rate": [
          {
            "uri": "*",
                "regex": ".*",
                "limit": [
                  {
                    "value": 10,
                    "verb": "POST",
                    "remaining": 2,
                    "unit": "MINUTE",
                    "next-available": "2011-12-15T22:42:45Z"
                  },
                  {
                    "value": 10,
                    "verb": "PUT",
                    "remaining": 2,
                    "unit": "MINUTE",
                    "next-available": "2011-12-15T22:42:45Z"
                  },
                  {
                    "value": 100,
                    "verb": "DELETE",
                    "remaining": 100,
                    "unit": "MINUTE",
                    "next-available": "2011-12-15T22:42:45Z"
                  }
                ]
          },
          {
            "uri": "*changes-since*",
            "regex": "changes-since",
            "limit": [
              {
                "value": 3,
                "verb": "GET",
                "remaining": 3,
                "unit": "MINUTE",
                "next-available": "2011-12-15T22:42:45Z"
              }
            ]
          },
          {
            "uri": "*/servers",
            "regex": "^/servers",
            "limit": [
              {
                "verb": "POST",
                "value": 25,
                "remaining": 24,
                "unit": "DAY",
                "next-available": "2011-12-15T22:42:45Z"
              }
            ]
          }
        ],
        "absolute": {
            "maxTotalRAMSize": 51200,
            "totalRAMUsed": 1024,
            "maxServerMeta": 5,
            "maxImageMeta": 5,
            "maxPersonality": 5,
            "maxPersonalitySize": 10240
        }
      }
   }




