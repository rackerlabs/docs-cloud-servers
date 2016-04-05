.. _get-services:

Get a list of services
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /services

This operation lists the available services.  

The following table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |Successful               |The request succeeded.   |
+--------------------------+-------------------------+-------------------------+
|400                       |Error                    |A general error has      |
|                          |                         |occured.                 |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |Unauthorized.            |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Forbidden.               |
+--------------------------+-------------------------+-------------------------+
|405                       |Bad Method               |Bad method.              |
+--------------------------+-------------------------+-------------------------+
|409                       |Conflicting Reqest       |Conflicting request.     |
+--------------------------+-------------------------+-------------------------+
|413                       |Over Limit               |The number of items      |
|                          |                         |returned is above the    |
|                          |                         |allowed limit.           |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+

Request
""""""""""""""""

This operation does not accept a request body.


Response
""""""""""""""""

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
| report_count   | The report count.                                         |
+----------------+-----------------------------------------------------------+
| topic          | The service type.                                         |
+----------------+-----------------------------------------------------------+
| updated_at     | If the service was updated, the date and timestamp of the |
|                | latest update.                                            |
+----------------+-----------------------------------------------------------+

**Response: List services**


.. code::

   Status Code: 200 OK
   Content-Length: 710
   Content-Type: application/json
   Date: Thu, 04 Dec 2014 21:45:47 GMT


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