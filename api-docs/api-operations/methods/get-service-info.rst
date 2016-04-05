.. _get-service-info:

Show basic service information
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /services/{service_id}

This shows information for a specified service.

Specify the ID for the service as ``service_id`` in the URI.

Request
""""""""""""""""

This operation does not accept a request body.


Response
""""""""""""""""

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
| report_count   | The report count.                                         |
+----------------+-----------------------------------------------------------+
| topic          | The service type.                                         |
+----------------+-----------------------------------------------------------+
| updated_at     | If the service was updated, the date and timestamp of the |
|                | latest update.                                            |
+----------------+-----------------------------------------------------------+


**Response: List services**

.. code::  

    HTTP/1.1 200 OK
    Content-Type: application/json
    Content-Length: 190
    Date: Wed, 08 Feb 2012 18:40:10 GMT

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
