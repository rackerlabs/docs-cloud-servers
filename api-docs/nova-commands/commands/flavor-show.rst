.. _nc-get-flavor-details:

Get flavor details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Shows information for a specified flavor.

**Usage:**

.. code::  

    $ nova flavor-show <flavor>

**Positional argument:**

-  ``flavor``. The name or ID of the flavor.

**Standard and Performance Server Outputs:**

.. code::  

    +--------------------------+-----------------------+
    | Property                 | Value                 |
    +--------------------------+-----------------------+
    | OS-FLV-DISABLED:disabled | False                 |
    | disk                     | 40                    |
    | id                       | 3                     |
    | name                     | 1GB Standard Instance |
    | ram                      | 1024                  |
    | rxtx_factor              | 3.0                   |
    | swap                     | 1024                  |
    | vcpus                    | 1                     |
    +--------------------------+-----------------------+
                    

.. code::  

    +-----------------------------------+-----------------------------------------------------------------------------+
    | Property                          | Value                                                                       |
    +-----------------------------------+-----------------------------------------------------------------------------+
    | OS-FLV-EXT-DATA:ephemeral         | 150                                                                         |
    | OS-FLV-WITH-EXT-SPECS:extra_specs | {u'resize_policy_class': u'performance_flavor', u'class': u'performance2',  |
    |     (cont.)                       |  u'disk_io_index': u'40', u'number_of_data_disks': u'1'}                    |
    | disk                              | 40                                                                          |
    | extra_specs                       | {u'resize_policy_class': u'performance_flavor', u'class': u'performance2',  |
    |     (cont.)                       |  u'disk_io_index': u'40', u'number_of_data_disks': u'1'}                    |
    | id                                | performance2-15                                                             |
    | name                              | 15 GB Performance                                                           |
    | ram                               | 15360                                                                       |
    | rxtx_factor                       | 1250.0                                                                      |
    | swap                              |                                                                             |
    | vcpus                             | 4                                                                           |
    +-----------------------------------+-----------------------------------------------------------------------------+                
                    

**Corresponding API call:** 
:rax-devdocs:`Show flavor details<cloud-servers/v2/developer-guide/#retrieve-flavor-details>`
