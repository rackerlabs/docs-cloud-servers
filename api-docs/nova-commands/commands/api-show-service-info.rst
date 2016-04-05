=========================================================================================================
Show Service Information - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
=========================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  Show Service Information
   :name: show-service-information
   :class: title

Verb
URI
Description
**GET**
/services/``id``
Shows information for a specified service.

This operation does not require a request body.

Specify the ID for the service as ``id`` in the URI.

This operation returns a response body.

The response body includes the following information:

+----------------+-----------------------------------------------------------+
| Field          | Description                                               |
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
| id             | The service ID.                                           |
+----------------+-----------------------------------------------------------+
| report\_count  | The report count.                                         |
+----------------+-----------------------------------------------------------+
| topic          | The service type.                                         |
+----------------+-----------------------------------------------------------+
| updated\_at    | If the service was updated, the date and timestamp of the |
|                | latest update.                                            |
+----------------+-----------------------------------------------------------+

Table: Table 17. Show Service Information Response Fields

**Example cURL command:**

.. code::  

    curl -v -X GET \
            -H "X-Auth-Project-Id: openstack" \
            -H"X-Auth-Token: rick:openstack" \
            127.0.0.1:8774/v2/openstack/services/1 | ppjson

**Example output:**

.. code::  

    > GET /v2/openstack/services/1 HTTP/1.1
    > User-Agent: curl/7.21.0 (x86_64-pc-linux-gnu) libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.15 libssh2/1.2.6
    > Host: 127.0.0.1:8774
    > Accept: */*
    > X-Auth-Project-Id: openstack
    > X-Auth-Token: rick:openstack
    > 
    < HTTP/1.1 200 OK
    < Content-Type: application/json
    < Content-Length: 190
    < Date: Wed, 08 Feb 2012 18:40:10 GMT
    <

.. code::  

    {
        "service": {
            "disabled": false, 
            "host": "squeeze", 
            "href": "http://127.0.0.1:8774/v2/services/1", 
            "id": 1, 
            "report_count": 764454, 
            "topic": "compute", 
            "updated_at": "2012-02-08 18:40:01"
        }
    }
