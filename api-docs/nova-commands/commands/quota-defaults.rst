.. _nc-list-default-quotas:

List default quotas for a tenant
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists the default quotas for a specified tenant.

**Usage:**

.. code::  

    $ nova quota-defaults --tenant <tenant_id>

**Optional argument:**

-  ``--tenant`` ``tenant-id``. The UUID or name of the tenant for which you want to list 
   the default quotas.

**Output:**

.. code::  

    +-----------------------------+-------+
    | Property                    | Value |
    +-----------------------------+-------+
    | cores                       | -1    |
    | floating_ips                | 5     |
    | gigabytes                   | -1    |
    | injected_file_content_bytes | 10240 |
    | injected_files              | 5     |
    | instances                   | 50    |
    | metadata_items              | 20    |
    | ram                         | 66560 |
    | volumes                     | 0     |
    +-----------------------------+-------+
