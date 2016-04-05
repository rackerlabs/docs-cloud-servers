.. _nc-show-service-details:

Show service details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Shows detailed information for a specified service.

.. code::  

    nova service-details <id>

**Positional argument:**

-  ``id``. The ID of the service for which you want to show detailed information.

**Output:**

.. code::  

    +------------------------+-------+
    |        Property        | Value |
    +------------------------+-------+
    | cpu_info               | 8     |
    | hypervisor_type        | xen   |
    | hypervisor_version     | 0     |
    | local_gb               | 265   |
    | local_gb_used          | 23    |
    | memory_mb              | 32767 |
    | memory_mb_used         | 2216  |
    | memory_mb_used_servers | 256   |
    | vcpus                  | 0     |
    | vcpus_used             | 0     |
    +------------------------+-------+

For example, the compute service shows hypervisor information.

Other services show information specific to the service.

**Corresponding API call:** 
