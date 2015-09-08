
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _get-retrieve-list-of-limits-including-used-limits-limits:

Retrieve list of limits including used limits
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /limits

Retrieves the current rate limits and absolute limits for your account including used 				limits.

This extension expands the limits operation to show the project usage, including RAM and instance quotas 				usage.

In the following example, the ``totalRAMUsed`` value is an extended attribute.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Success                  |Request succeeded.       |
+--------------------------+-------------------------+-------------------------+
|400                       |Error                    |A general error has      |
|                          |                         |occured.                 |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |Unauthorized.            |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Forbidden.               |
+--------------------------+-------------------------+-------------------------+
|405                       |Bad Method               |Bad method.              |
+--------------------------+-------------------------+-------------------------+
|409                       |Conflicting Reqest       |Conflicting request.     |
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


Request
""""""""""""""""








This operation does not accept a request body.




Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|limits                    |Object                   |The container of limits  |
|                          |                         |attributes.              |
+--------------------------+-------------------------+-------------------------+
|absolute                  |Object                   |The container of         |
|                          |                         |absolute limits          |
|                          |                         |attributes.              |
+--------------------------+-------------------------+-------------------------+
|maxTotalRAMSize           |Int                      |The maximum amount of    |
|                          |                         |RAM allowed.             |
+--------------------------+-------------------------+-------------------------+
|totalRAMUsed              |Int                      |The total amount of RAM  |
|                          |                         |used.                    |
+--------------------------+-------------------------+-------------------------+
|maxServerMeta             |Int                      |The maximum allowed      |
|                          |                         |server metadata items.   |
+--------------------------+-------------------------+-------------------------+
|maxImageMeta              |Int                      |The maximum allowed      |
|                          |                         |image metadata items.    |
+--------------------------+-------------------------+-------------------------+
|maxPersonality            |Int                      |The maximum number of    |
|                          |                         |personality files.       |
+--------------------------+-------------------------+-------------------------+
|maxPersonalitySize        |Int                      |The size of the          |
|                          |                         |personality files.       |
+--------------------------+-------------------------+-------------------------+
|rate                      |Array                    |The array of rate        |
|                          |                         |objects.                 |
+--------------------------+-------------------------+-------------------------+
|limit                     |Array                    |The array of rate limit  |
|                          |                         |objects.                 |
+--------------------------+-------------------------+-------------------------+
|next-available            |Date                     |The next available rate  |
|                          |                         |limit date and time.     |
+--------------------------+-------------------------+-------------------------+
|verb                      |String                   |The HTTP operation.      |
+--------------------------+-------------------------+-------------------------+
|value                     |String                   |The max allowed time in  |
|                          |                         |units.                   |
+--------------------------+-------------------------+-------------------------+
|remaining                 |Date                     |The time remaining for   |
|                          |                         |the rate limit in units. |
+--------------------------+-------------------------+-------------------------+
|unit                      |Date                     |The type of unit for the |
|                          |                         |rate limit. For example, |
|                          |                         |``DAY`` or ``MINUTE``.   |
+--------------------------+-------------------------+-------------------------+







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




