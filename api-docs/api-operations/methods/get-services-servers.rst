.. _get-services-servers:

Get a list of servers for a service
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /services/{service_id}/servers

This operation lists the servers that are associated with a specified service.  

Specify the ID for the service as ``service_id`` in the URI.

The following table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Successful               |The request succeeded.   |
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
The response body includes the following information:

+----------------+-----------------------------------------------------------+
| Name           | Description                                               |
+================+===========================================================+
| accessIPv6     | Not in use.                                               |
+----------------+-----------------------------------------------------------+
| accessIPv4     | Not in use.                                               |
+----------------+-----------------------------------------------------------+
| addresses      | Public and private IP addresses, The ``version`` field    |
|                | indicates whether the IP address is version 4 or 6.       |
+----------------+-----------------------------------------------------------+
| config_drive   | The configuration drive, if any.                          |
+----------------+-----------------------------------------------------------+
| created        | The time stamp for the creation date.                     |
+----------------+-----------------------------------------------------------+
| flavor         | The flavor reference, including the flavor ID and the     |
|                | full URL.                                                 |
+----------------+-----------------------------------------------------------+
| hostId         | The host ID.                                              |
+----------------+-----------------------------------------------------------+
| id             | The server ID.                                            |
+----------------+-----------------------------------------------------------+
| image          | The image reference, including the image ID and the full  |
|                | URL.                                                      |
+----------------+-----------------------------------------------------------+
| key_name       | The key name, if any.                                     |
+----------------+-----------------------------------------------------------+
| links          | Server links.                                             |
+----------------+-----------------------------------------------------------+
| metadata       | Metadata key and value pairs, if any.                     |
+----------------+-----------------------------------------------------------+
| name           | The server name.                                          |
+----------------+-----------------------------------------------------------+
| progress       | The percentage built.                                     |
+----------------+-----------------------------------------------------------+
| status         | The server status.                                        |
+----------------+-----------------------------------------------------------+
| tenant_id      | The tenant ID.                                            |
+----------------+-----------------------------------------------------------+
| updated        | The time stamp for the last update.                       |
+----------------+-----------------------------------------------------------+
| user_id        | The user ID.                                              |
+----------------+-----------------------------------------------------------+

**Example: List server for a service response**


.. code::

   Status Code: 200 OK
   Content-Length: 967
   Content-Type: application/json
   Date: Date: Wed, 08 Feb 2012 18:48:35 GMT


    {
        "servers": [
            {
                "accessIPv4": "", 
                "accessIPv6": "", 
                "addresses": {
                    "private": [
                        {
                            "addr": "10.0.0.38", 
                            "version": 4
                        }
                    ]
                }, 
                "config_drive": "", 
                "created": "2012-02-08T02:53:22Z", 
                "flavor": {
                    "id": "1", 
                    "links": [
                        {
                            "href": "http://127.0.0.1:8774/openstack/flavors/1", 
                            "rel": "bookmark"
                        }
                    ]
                }, 
                "hostId": "aa2e9509e419ded81924c50543bef1c3df387b564abb12a097a49ded", 
                "id": "fb243545-328f-422c-9949-ae35a336030a", 
                "image": {
                    "id": "1a6212db-c2b5-46e6-954f-50c685469364", 
                    "links": [
                        {
                            "href": "http://127.0.0.1:8774/openstack/images/1a6212db-c2b5-46e6-954f-50c685469364", 
                            "rel": "bookmark"
                        }
                    ]
                }, 
                "key_name": "", 
                "links": [
                    {
                        "href": "http://127.0.0.1:8774/v2/openstack/servers/fb243545-328f-422c-9949-ae35a336030a", 
                        "rel": "self"
                    }, 
                    {
                        "href": "http://127.0.0.1:8774/openstack/servers/fb243545-328f-422c-9949-ae35a336030a", 
                        "rel": "bookmark"
                    }
                ], 
                "metadata": {}, 
                "name": "apple", 
                "progress": 100, 
                "status": "RESIZE", 
                "tenant_id": "openstack", 
                "updated": "2012-02-08T04:59:16Z", 
                "user_id": "rick"
            }
        ]
    }