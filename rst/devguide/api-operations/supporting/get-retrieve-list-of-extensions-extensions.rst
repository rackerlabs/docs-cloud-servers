
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve list of extensions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /extensions

Retrieves the list of available extensions.





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




**Example Retrieve list of extensions: JSON request**


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
|extensions                |Array                    |The array of extensions. |
+--------------------------+-------------------------+-------------------------+
|updated                   |Date                     |The most recent update   |
|                          |                         |date for the extension.  |
+--------------------------+-------------------------+-------------------------+
|name                      |String                   |The name of the          |
|                          |                         |extension.               |
+--------------------------+-------------------------+-------------------------+
|links                     |Array                    |The array of links for   |
|                          |                         |the extension.           |
+--------------------------+-------------------------+-------------------------+
|namespace                 |String                   |The namespace of the     |
|                          |                         |extension.               |
+--------------------------+-------------------------+-------------------------+
|alias                     |String                   |The alias, or short      |
|                          |                         |name, of the extension.  |
+--------------------------+-------------------------+-------------------------+
|description               |String                   |The description of the   |
|                          |                         |extension.               |
+--------------------------+-------------------------+-------------------------+





**Example Retrieve list of extensions: JSON response**


.. code::

        Status Code: 200 OK
        Content-Length: 6045
        Content-Type: application/json
        Date: Fri, 10 Jul 2015 19:53:39 GMT, Fri, 10 Jul 2015 19:53:39 GMT
        Server: Jetty(9.2.z-SNAPSHOT)
        Via: 1.1 Repose (Repose/6.2.1.2)
        X-Compute-Request-Id: req-79e5a4fe-81ca-4965-b616-6935bab482b3


