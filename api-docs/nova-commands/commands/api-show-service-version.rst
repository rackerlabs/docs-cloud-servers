=====================================================================================================
Show Service Version - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
=====================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  Show Service Version
   :name: show-service-version
   :class: title

Verb
URI
Description
**GET**
/services/``id``/version
Shows the version for a specified service.

This operation does not require a request body.

Specify the ID for the service as ``id`` in the URI.

This operation returns a response body.

The response body includes version information for the service.

**Example cURL command:**

.. code::  

    curl -v -X GET \
            -H "X-Auth-Project-Id: openstack" \
            -H"X-Auth-Token: rick:openstack" \
            127.0.0.1:8774/v2/openstack/services/1/version | ppjson

**Example output:**

.. code::  

    > GET /v2/openstack/services/1/version HTTP/1.1
    > User-Agent: curl/7.21.0 (x86_64-pc-linux-gnu) libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.15 libssh2/1.2.6
    > Host: 127.0.0.1:8774
    > Accept: */*
    > X-Auth-Project-Id: openstack
    > X-Auth-Token: rick:openstack
    > 
    < HTTP/1.1 200 OK
    < Content-Type: application/json
    < Content-Length: 37
    < Date: Wed, 08 Feb 2012 18:54:32 GMT
    <

.. code::  

    {
        "version": {
            "string": "2012.1-dev"
            }
            }
