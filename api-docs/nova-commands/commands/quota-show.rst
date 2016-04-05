.. _nc-list-quotas:

List quotas for a tenant
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists the quotas for a specified tenant.

**Usage:**

.. code::  

    $ nova quota-show <tenant_id>

**Positional argument:**

-  ``tenant_id``. The ID of the tenant for which you want to list quotas.

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
