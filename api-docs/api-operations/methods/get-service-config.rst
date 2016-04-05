.. _get-service-configuration:

Show service configuration
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /services/{service_id}/config

This shows the configuration settings for a specified service.

Specify the ID for the service as ``service_id`` in the URI.


Request
""""""""""""""""

This operation does not accept a request body.

Response
""""""""""""""""

The response body includes any configuration flags and their values.

**Response: Show service configuration**


.. code::  

    HTTP/1.1 200 OK
    Content-Type: application/json
    Content-Length: 12063
    Date: Wed, 08 Feb 2012 18:51:56 GMT

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
     
