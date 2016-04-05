========================================================================================================
List Available Services - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
========================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  List Available Services
   :name: list-available-services
   :class: title

Verb
URI
Description
**GET**
/services
Lists the available services.

This operation does not require a request body.

This operation returns a response body.

The response body includes the following information:

+----------------+-----------------------------------------------------------+
| Name           | Description                                               |
+================+===========================================================+
| disabled       | Indicates whether the service is enabled or disabled:     |
|                |                                                           |
|                |                                                           |
|                |                                                           |
|                | -  ``false``. The service is enabled.                     |
|                |                                                           |
|                | -  ``true``. The service is disabled.                     |
|                |                                                           |
|                |                                                           |
+----------------+-----------------------------------------------------------+
| host           | The name of the host where the service is running.        |
+----------------+-----------------------------------------------------------+
| href           | The URL for the service.                                  |
+----------------+-----------------------------------------------------------+
| id             | The service ID. Use this ID to get more information about |
|                | and manage the service.                                   |
+----------------+-----------------------------------------------------------+
| report\_count  | The report count.                                         |
+----------------+-----------------------------------------------------------+
| topic          | The service type.                                         |
+----------------+-----------------------------------------------------------+
| updated\_at    | If the service was updated, the date and timestamp of the |
|                | latest update.                                            |
+----------------+-----------------------------------------------------------+

Table: Table 16. List Available Services Response Fields

**Example cURL command:**

.. code::  

    curl -v -X GET \
            -H "X-Auth-Project-Id: openstack" \
            -H"X-Auth-Token: rick:openstack" \
            127.0.0.1:8774/v2/openstack/services | ppjson

**Example output:**

.. code::  

    > GET /v2/openstack/services HTTP/1.1
    > User-Agent: curl/7.21.0 (x86_64-pc-linux-gnu) libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.15 libssh2/1.2.6
    > Host: 127.0.0.1:8774
    > Accept: */*
    > X-Auth-Project-Id: openstack
    > X-Auth-Token: rick:openstack
    >
    < HTTP/1.1 200 OK
    < Content-Type: application/json
    < Content-Length: 710
    < Date: Wed, 08 Feb 2012 18:34:17 GMT
    < 

.. code::  

    {
        "services": [
            {
                "disabled": false, 
                "host": "squeeze", 
                "href": "http://127.0.0.1:8774/v2/services/1", 
                "id": 1, 
                "report_count": 764419, 
                "topic": "compute", 
                "updated_at": "2012-02-08 18:34:10"
            }, 
            {
                "disabled": false, 
                "host": "squeeze", 
                "href": "http://127.0.0.1:8774/v2/services/2", 
                "id": 2, 
                "report_count": 775038, 
                "topic": "scheduler", 
                "updated_at": "2012-02-08 18:34:14"
            }, 
            {
                "disabled": false, 
                "host": "squeeze", 
                "href": "http://127.0.0.1:8774/v2/services/3", 
                "id": 3, 
                "report_count": 775054, 
                "topic": "network", 
                "updated_at": "2012-02-08 18:34:10"
            }, 
            {
                "disabled": false, 
                "host": "squeeze", 
                "href": "http://127.0.0.1:8774/v2/services/4", 
                "id": 4, 
                "report_count": 0, 
                "topic": "console", 
                "updated_at": null
            }
        ]
    }
