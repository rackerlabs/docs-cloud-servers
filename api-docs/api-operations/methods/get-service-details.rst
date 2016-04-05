.. _get-service-details:

Show service details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /services/{service_id}/details

This shows detailed information for a specified service. For example, the response body for 
the compute service shows hypervisor information.

Specify the ID for the service as ``service_id`` in the URI.

Request
""""""""""""""""

This operation does not accept a request body.


Response
""""""""""""""""

**Response: List services**

.. code::  

    HTTP/1.1 200 OK
    Content-Type: application/json
    Content-Length: 221
    Date: Wed, 08 Feb 2012 18:45:18 GMT

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
