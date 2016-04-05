.. _nc-show-service:

Show basic service information
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Shows basic information for a specified service.

**Usage:**

.. code::  

    nova service-show <id>

**Positional argument:**

-  ``id``. The ID of the service for which you want to show details.

**Output:**

.. code::  

    +--------------+------------------------------------------+
    |   Property   |                  Value                   |
    +--------------+------------------------------------------+
    | disabled     | False                                    |
    | host         | squeeze                                  |
    | href         | http://10.127.4.222:8774/v2/services/1   |
    | id           | 1                                        |
    | report_count | 704789                                   |
    | topic        | compute                                  |
    | updated_at   | 2012-02-01 19:15:39                      |
    +--------------+------------------------------------------+

The command lists the following information:

+----------------+-----------------------------------------------------------+
| Field          | Description                                               |
+================+===========================================================+
| disabled       | Indicates whether the service is enabled or disabled:     |
|                |                                                           |
|                |                                                           |
|                |                                                           |
|                | -  ``False``. The service is enabled.                     |
|                |                                                           |
|                | -  ``True``. The service is disabled.                     |
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

**Corresponding API call:** 
