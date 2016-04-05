===========================================================================================================
List Servers for a Service - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
===========================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  List Servers for a Service
   :name: list-servers-for-a-service
   :class: title

Verb
URI
Description
**GET**
/services/``id``/servers
Lists servers associated with a specified service.

This operation does not require a request body.

Specify the ID for the service as ``id`` in the URI.

This operation returns a response body.

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
| config\_drive  | The configuration drive, if any.                          |
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
| key\_name      | The key name, if any.                                     |
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
| tenant\_id     | The tenant ID.                                            |
+----------------+-----------------------------------------------------------+
| updated        | The time stamp for the last update.                       |
+----------------+-----------------------------------------------------------+
| user\_id       | The user ID.                                              |
+----------------+-----------------------------------------------------------+

Table: Table 18. List Server for a Service Response Fields

**Example cURL command:**

.. code::  

    $ curl -v -X GET \
            -H "X-Auth-Project-Id: openstack" \
            -H"X-Auth-Token: rick:openstack" \
            127.0.0.1:8774/v2/openstack/services/1/servers | ppjson

**Example output:**

.. code::  

    > GET /v2/openstack/services/1/servers HTTP/1.1
    > User-Agent: curl/7.21.0 (x86_64-pc-linux-gnu) libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.15 libssh2/1.2.6
    > Host: 127.0.0.1:8774
    > Accept: */*
    > X-Auth-Project-Id: openstack
    > X-Auth-Token: rick:openstack
    > 
    < HTTP/1.1 200 OK
    < Content-Type: application/json
    < Content-Length: 967
    < Date: Wed, 08 Feb 2012 18:48:35 GMT
    <

.. code::  

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
