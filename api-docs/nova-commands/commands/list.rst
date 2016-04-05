.. _nc-list-servers:

Retrieve list of servers 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists active servers.

**Usage:**

.. code::  

    $ nova list [--reservation_id <reservation_id>] [--ip <ip_regexp>]
                [--ip6 <ip6_regexp>] [--name <name_regexp>]
                [--instance_name <name_regexp>] [--status <status>]
                [--flavor <flavor>] [--image <image>] [--host <hostname>]
                [--all_tenants [0|1]]

**Optional arguments:**

-  **--reservation_id** ``reservation_id``. Returns instances that match the specified 
   reservation ID.

-  **--ip** ``ip_regexp``. Returns instances that match the specified IP address regular 
   expression.

-  **--name** ``nav_regexp``. Returns instances that match the specified name regular 
   expression.

-  **--instance_name** ``name_regexp``. Returns instances that match the specified 
   instance name regular expression.

-  **--status** ``status``. Returns instances that match the specified status.

-  **--flavor** ``flavor``. Returns instances that match the specified flavor.

-  **--image** ``image``. Retuns instances that match the specified image.

-  **--host** ``hostname``. Returns instances that match the specified host name.

-  **--all_tenants** ``[0|1]``. Set to 1 to return instances for all tenants (Admin only).

**Output:** Servers are listed by server ID.

.. code::  

    +--------------------------------------+-------+--------+----------+
    | ID                                   | Name  | Status | Networks |
    +--------------------------------------+-------+--------+----------+
    | 59b830be-5add-4ae3-b8c0-01120b4746d2 | test  | ERROR  |          |
    | 9b5245d0-c0f6-4bf7-a16d-4e90fd2f880e | test  | ERROR  |          |
    | 3594ed4f-fcf8-4a11-9713-f506e9e47cdf | test2 | ERROR  |          |
    +--------------------------------------+-------+--------+----------+

The command lists the following information:

+----------------+-----------------------------------------------------------+
| Name           | Description                                               |
+================+===========================================================+
| ID             | The server ID.                                            |
+----------------+-----------------------------------------------------------+
| Name           | The server name.                                          |
+----------------+-----------------------------------------------------------+
| Status         | The server status.                                        |
+----------------+-----------------------------------------------------------+
| Networks       | The public and private IP addresses for the server.       |
+----------------+-----------------------------------------------------------+

**Corresponding API call:**
:rax-devdocs:`Retrieve list of servers<cloud-servers/v2/developer-guide/#retrieve-list-of-servers>`
