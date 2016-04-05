.. _nc-list-services:

List services
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists available services with attributes.

**Usage:**

.. code::  

    nova service-list

**Output:**

.. code::  

    +----+-----------+---------+----------+--------------+---------------------+
    | ID |   topic   |   host  | disabled | report_count |      updated_at     |
    +----+-----------+---------+----------+--------------+---------------------+
    | 1  | compute   | squeeze | False    | 704782       | 2012-02-01 19:14:28 |
    | 2  | scheduler | squeeze | False    | 714968       | 2012-02-01 19:14:34 |
    | 3  | network   | squeeze | False    | 714983       | 2012-02-01 19:14:26 |
    | 4  | console   | squeeze | False    | 0            | None                |
    +----+-----------+---------+----------+--------------+---------------------+

The command lists the following information:

+----------------+-----------------------------------------------------------+
| Field          | Description                                               |
+================+===========================================================+
| ID             | The service ID. Use this ID to get more information about |
|                | and manage the service.                                   |
+----------------+-----------------------------------------------------------+
| topic          | The service type.                                         |
+----------------+-----------------------------------------------------------+
| host           | The name of the host where the service is running.        |
+----------------+-----------------------------------------------------------+
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
| report_count   | The report count.                                         |
+----------------+-----------------------------------------------------------+
| updated_at     | If the service was updated, the date and timestamp of the |
|                | latest update.                                            |
+----------------+-----------------------------------------------------------+

**Corresponding API call:** 
