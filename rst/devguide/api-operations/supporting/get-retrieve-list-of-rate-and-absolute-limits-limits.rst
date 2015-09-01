
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve list of rate and absolute limits
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /limits

Retrieves the current rate limits and absolute limits for your account.

Applications can programmatically determine current account limits by using this API operation.



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
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""






This operation does not accept a request body.




**Example Retrieve list of rate and absolute limits: JSON request**


.. code::

    X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
    Content-Type: application/json
    Accept: application/json


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





**Example Retrieve list of rate and absolute limits: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 3010
        Content-Type: application/json
        Date: Wed, 18 Mar 2015 20:23:18 GMT, Wed, 18 Mar 2015 20:23:19 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-48d05db0-dd97-4aef-87f2-11177ab8c262


