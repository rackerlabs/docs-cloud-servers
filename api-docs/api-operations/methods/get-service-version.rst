.. _get-service-version:

Show service version
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /services/{service_id}/version

This operation shows the version for a specified service.

Specify the ID for the service as ``service_id`` in the URI.

Request
""""""""""""""""

This operation does not accept a request body.


Response
""""""""""""""""

**Response: Show service version**

.. code::  

    HTTP/1.1 200 OK
    Content-Type: application/json
    Content-Length: 37
    Date: Wed, 08 Feb 2012 18:54:32 GMT


.. code::  

    {
        "version": {
            "string": "2012.1-dev"
         }
    }
