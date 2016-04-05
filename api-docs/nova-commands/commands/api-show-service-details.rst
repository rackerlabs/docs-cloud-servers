=====================================================================================================
Show Service Details - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
=====================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  Show Service Details
   :name: show-service-details
   :class: title

Verb
URI
Description
**GET**
/services/``id``/details
Shows detailed information for a specified service.

This operation does not require a request body.

Specify the ID for the service as ``id`` in the URI.

This operation returns a response body.

For example, the response body for the compute service shows hypervisor
information.

The response body for other services shows information specific to the
service.

**Example cURL command:**

.. code::  

    curl -v -X GET \
            -H "X-Auth-Project-Id: openstack" \
            -H"X-Auth-Token: rick:openstack" \
            127.0.0.1:8774/v2/openstack/services/1/details | ppjson

**Example output:**

.. code::  

    > GET /v2/openstack/services/1/details HTTP/1.1
    > User-Agent: curl/7.21.0 (x86_64-pc-linux-gnu) libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.15 libssh2/1.2.6
    > Host: 127.0.0.1:8774
    > Accept: */*
    > X-Auth-Project-Id: openstack
    > X-Auth-Token: rick:openstack
    > 
    < HTTP/1.1 200 OK
    < Content-Type: application/json
    < Content-Length: 221
    < Date: Wed, 08 Feb 2012 18:45:18 GMT
    <

.. code::  

    {
        "details": {
            "cpu_info": "8", 
            "hypervisor_type": "xen", 
            "hypervisor_version": 0, 
            "local_gb": 229, 
            "local_gb_used": 21, 
            "memory_mb": 32767, 
            "memory_mb_used": 2282, 
            "memory_mb_used_servers": 0, 
            "vcpus": 0, 
            "vcpus_used": 0
        }
    }
