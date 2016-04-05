.. _nc-get-absolute-limits:

Get absolute limits 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists absolute limits for a user.

**Usage:**

.. code::  

    $ nova absolute-limits

**Output:**

.. code::  

    +-------------------------+-------+
    | Name                    | Value |
    +-------------------------+-------+
    | maxImageMeta            | 20    |
    | maxPersonality          | 5     |
    | maxPersonalitySize      | 10240 |
    | maxServerMeta           | 20    |
    | maxTotalCores           | -1    |
    | maxTotalFloatingIps     | 5     |
    | maxTotalInstances       | 50    |
    | maxTotalKeypairs        | 100   |
    | maxTotalRAMSize         | 66560 |
    | maxTotalVolumeGigabytes | -1    |
    | maxTotalVolumes         | 0     |
    +-------------------------+-------+

The response includes the following information:

+----------------+-----------------------------------------------------------+
| Field          | Description                                               |
+================+===========================================================+
| Name           | The name of the absolute limit. The ``max`` limits show   |
|                | the maximum amount of a resource that can be used. The    |
|                | ``total`` limits show current usage.                      |
+----------------+-----------------------------------------------------------+
| Value          | The value for the absolute limit. A negative value        |
|                | indicates that the limit is disabled.                     |
+----------------+-----------------------------------------------------------+

**Corresponding API call:** 
:rax-devdocs:`Retrieve list of rate and absolute limits<cloud-servers/v2/developer-guide/#retrieve-list-of-rate-and-absolute-limits>`
