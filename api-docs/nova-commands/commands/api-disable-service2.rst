================================================================================================
Disable Service - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  Disable Service
   :name: disable-service
   :class: title

Verb
URI
Description
**POST**
/services/``id``/disable
Disables the specified service.
Specify the service ID as ``id`` in the URI.

The request does not require a request body.

The response does not return a response body.

**Example cURL command:**

.. code::  

    curl -v -X POST \
           -H "X-Auth-Project-Id: openstack" \
           -H"X-Auth-Token: rick:openstack" \
           127.0.0.1:8774/v2/openstack/services/1/disable

**Example output:**

.. code::  

    > POST /v2/openstack/services/1/disable HTTP/1.1
    > User-Agent: curl/7.21.0 (x86_64-pc-linux-gnu) libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.15 libssh2/1.2.6
    > Host: 127.0.0.1:8774
    > Accept: */*
    > X-Auth-Project-Id: openstack
    > X-Auth-Token: rick:openstack
    > 
    < HTTP/1.1 200 OK
    < Content-Length: 0
    < Content-Type: application/json
    < Date: Wed, 08 Feb 2012 18:58:21 GMT
