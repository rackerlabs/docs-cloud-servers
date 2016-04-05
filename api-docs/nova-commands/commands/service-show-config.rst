.. _nc-show-service-config:

Show service configuration
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Shows the flag configurations for a specified service.

**Usage:**

.. code::  

    nova service-config <id>

**Positional argument:**

-  ``id``. The ID of the service for which you want to show flag configurations.

**Output:**

.. code::  

    +------------------------+-------+
    |        Property        | Value |
    +------------------------+-------+
    | flag                   | 0     |
    +------------------------+-------+

The output shows the value for each configuration flag.

**Corresponding API call:** 
