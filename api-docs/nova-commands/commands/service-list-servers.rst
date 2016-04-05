.. _nc-list-service-servers:

List servers for a service
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists servers that belong to a specified service.

**Usage:**

.. code::  

    nova service-servers <id>

**Positional argument:**

-  ``id``. The ID of the service for which you want to list servers.

**Output:**

.. code::  

    +--------------------------------------+------------+--------+-------------------+
    |                  ID                  |    Name    | Status |      Networks     |
    +--------------------------------------+------------+--------+-------------------+
    | 855f28fd-1d89-4a7d-b5a5-f4dd54e83550 | apple      | ACTIVE | private=10.0.0.34 |
    | dae7b332-de5d-4fdd-a82b-1354e5b69f88 | dewberry   | ACTIVE | private=10.0.0.37 |
    | f057f9ca-77db-445c-9867-77da79006232 | cherry     | ACTIVE | private=10.0.0.36 |
    | f64687c3-9f93-46a0-81b8-be65d8286a69 | blackberry | ACTIVE | private=10.0.0.35 |
    +--------------------------------------+------------+--------+-------------------+

The command lists the following information:

+----------------+-----------------------------------------------------------+
| Field          | Description                                               |
+================+===========================================================+
| ID             | The server ID.                                            |
+----------------+-----------------------------------------------------------+
| Name           | The server name.                                          |
+----------------+-----------------------------------------------------------+
| Status         | The server status.                                        |
+----------------+-----------------------------------------------------------+
| Networks       | The private and public networks for the server.           |
+----------------+-----------------------------------------------------------+

**Corresponding API call:** 
