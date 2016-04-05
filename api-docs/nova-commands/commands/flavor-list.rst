.. _nc-list-flavors:

List flavors
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists flavors.

**Usage:**

.. code::  

    $ nova flavor-list

Optional parameter: ``--extra-specs``

The command returns details that describe each flavor.

**ID**
    Flavor ID

**Name**
    Flavor name

**Memory_MB**
    Amount of memory

**Disk**
    Size of disk in GB (for Performance flavors, the size of the system disk)

**Ephemeral**
    Size of data disks in GB for Performance flavors

**Swap**
    Size of swap space

**VCPUs**
    Number of virtual CPUs

**RXTX_Factor**
    Amount of bandwidth, in Mbps, allocated to the PublicNet ports, ServiceNet ports, and 
    isolated networks (Cloud Networks) attached to a server

**Is_Public**
    Not used

**extra_specs**
    Extra specifications

    **Class**
        flavor class: standard1, performance1, or performance2

    **Disk_io_index**
        Relative measure of disk I/O performance from 0-99, where higher is faster 
        (Performance flavors only)

    **Number_of_data_disks**
        Number of data disks (Performance flavors only)

**Output:**

You will see one of the following possible result sets, depending on whether the region 
you selected supports Performance flavors:

..  note:: 

    In order to see the extra-specs column, pass ``--extra-specs`` argument in command.

.. code::  

                                                                Flavor List
    +------------------+-------------------------+---------+------+--------+------+-------+---------+--------+------------------------------------------------------------------------------------------------------------------------------------+
    | ID               | Name                    | Memory_ | Disk | Eph-   | Swap | VCPUs | RXTX_   | Is_    | extra_specs                                                                                                                        |
    |                  |                         | MB      |      | emeral |      |       | Factor  | Public |                                                                                                                                    |
    +------------------+-------------------------+---------+------+--------+------+-------+---------+--------+------------------------------------------------------------------------------------------------------------------------------------+ 
    | 2                | 512MB Standard Instance | 512     | 20   | 0      | 512  | 1     | 80.0    | N/A    | {u'class': u'standard1', u'disk_io_index': u'2', u'number_of_data_disks': u'0'}                                                    |
    | 3                | 1GB Standard Instance   | 1024    | 40   | 0      | 1024 | 1     | 120.0   | N/A    | {u'class': u'standard1', u'disk_io_index': u'2', u'number_of_data_disks': u'0'}                                                    |
    | 4                | 2GB Standard Instance   | 2048    | 80   | 0      | 2048 | 2     | 240.0   | N/A    | {u'class': u'standard1', u'disk_io_Index': u'2', u'number_of_data_disks': u'0'}                                                    |
    | 5                | 4GB Standard Instance   | 4096    | 160  | 0      | 2048 | 2     | 400.0   | N/A    | {u'class': u'standard1', u'disk_io_index': u'2', u'number_of_data_disks': u'0'}                                                    |
    | 6                | 8GB Standard Instance   | 8192    | 320  | 0      | 2048 | 4     | 600.0   | N/A    | {u'class': u'standard1', u'disk_io_index': u'2', u'number_of_data_disks': u'0'}                                                    |
    | 7                | 15GB Standard Instance  | 15360   | 620  | 0      | 2048 | 6     | 800.0   | N/A    | {u'class': u'standard1', u'disk_io_index': u'2', u'number_of_data_disks': u'0'}                                                    |
    | 8                | 30GB Standard Instance  | 30720   | 1200 | 0      | 2048 | 8     | 1200.0  | N/A    | {u'class': u'standard1', u'disk_io_index': u'2', u'number_of_data_disks': u'0'}                                                    |
    | performance1-1   | 1 GB Performance        | 1024    | 20   | 0      |      | 1     | 200.0   | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance1', u'disk_io_index': u'40', u'number_of_data_disks': u'0'} |
    | performance1-2   | 2 GB Performance        | 2048    | 40   | 20     |      | 2     | 400.0   | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance1', u'disk_io_index': u'40', u'number_of_data_disks': u'1'} |
    | performance1-4   | 4 GB Performance        | 4096    | 40   | 40     |      | 4     | 800.0   | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance1', u'disk_io_index': u'40', u'number_of_data_disks': u'1'} |
    | performance1-8   | 8 GB Performance        | 8192    | 40   | 80     |      | 8     | 1600.0  | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance1', u'disk_io_index': u'40', u'number_of_data_disks': u'1'} |
    | performance2-120 | 120 GB Performance      | 122880  | 40   | 1200   |      | 32    | 10000.0 | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance2', u'disk_io_index': u'80', u'number_of_data_disks': u'4'} |
    | performance2-15  | 15 GB Performance       | 15360   | 40   | 150    |      | 4     | 1250.0  | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance2', u'disk_io_index': u'40', u'number_of_data_disks': u'1'} |
    | performance2-30  | 30 GB Performance       | 30720   | 40   | 300    |      | 8     | 2500.0  | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance2', u'disk_io_index': u'40', u'number_of_data_disks': u'1'} |
    | performance2-60  | 60 GB Performance       | 61440   | 40   | 600    |      | 16    | 5000.0  | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance2', u'disk_io_index': u'60', u'number_of_data_disks': u'2'} |
    | performance2-90  | 90 GB Performance       | 92160   | 40   | 900    |      | 24    | 7500.0  | N/A    | {u'resize_policy_class': u'performance_flavor', u'class': u'performance2', u'disk_io_index': u'70', u'number_of_data_disks': u'3'} |
    +------------------+-------------------------+---------+------+--------+------+-------+---------+--------+------------------------------------------------------------------------------------------------------------------------------------+

**Corresponding API call:** **Corresponding API call:** 
:rax-devdocs:`Retrieve list of flavors<cloud-servers/v2/developer-guide/#retrieve-list-of-flavors>`
