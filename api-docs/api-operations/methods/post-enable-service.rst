.. _post-enable-service:

Enable service
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /services/{service_id}/enable

Enables a specified service that is disabled.

Specify the service ID as ``service_id`` in the URI.

Request
""""""""""""""""

This operation does not accept a request body.


Response
""""""""""""""""

**Example: Enable services response**

.. code::

   Status Code: 200 OK
   Content-Length: 0
   Content-Type: application/json
   Date: Thu, 04 Dec 2014 21:45:47 GMT