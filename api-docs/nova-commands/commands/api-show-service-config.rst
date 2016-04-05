=======================================================================================================================
Show Service Configuration Information - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
=======================================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  Show Service Configuration Information
   :name: show-service-configuration-information
   :class: title

Verb
URI
Description
**GET**
/services/``id``/config
Shows the configuration settings for a specified service.

This operation does not require a request body.

Specify the ID for the service as ``id`` in the URI.

This operation returns a response body.

The response body includes any configuration flags and their values.

**Example cURL command:**

.. code::  

    curl -v -X GET \
            -H "X-Auth-Project-Id: openstack" \
            -H"X-Auth-Token: rick:openstack" \
            127.0.0.1:8774/v2/openstack/services/1/config | ppjson

**Example output:**

.. code::  

    > GET /v2/openstack/services/1/config HTTP/1.1
    > User-Agent: curl/7.21.0 (x86_64-pc-linux-gnu) libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.15 libssh2/1.2.6
    > Host: 127.0.0.1:8774
    > Accept: */*
    > X-Auth-Project-Id: openstack
    > X-Auth-Token: rick:openstack
    >
    < HTTP/1.1 200 OK
    < Content-Type: application/json
    < Content-Length: 12063
    < Date: Wed, 08 Feb 2012 18:51:56 GMT
    <

.. code::  

    {
        "config": {
            "agent_version_timeout": 300,
            "ajax_console_proxy_port": 8000,
            "ajax_console_proxy_topic": "ajax_proxy",
            "ajax_console_proxy_url": "http://127.0.0.1:8000",
            "ajaxterm_portrange": "10000-12000",  
            "allow_resize_to_same_host": true,
            "allow_same_net_traffic": true,
            "allowed_roles": [
                "cloudadmin",
                "itsec",
                "sysadmin",
                "netadmin",
                "developer"
            ],
     ... (more) ...
           }
     }
     
