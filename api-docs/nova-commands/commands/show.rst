.. _nc-show-server:

Get server details 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Shows details for a specified server.

**Usage:**

.. code::  

    $ nova show <server>

**Optional argument:**

-  ``server``. The name or ID of the server for which you want details.

**Output:**

.. code::  

    +-------------------------------------+----------------------------------------------------------------+
    | Property                            | Value                                                          |
    +-------------------------------------+----------------------------------------------------------------+
    | OS-DCF:diskConfig                   | MANUAL                                                         |
    | OS-EXT-AZ:availability_zone         | nova                                                           |
    | OS-EXT-SRV-ATTR:host                | devstack-grizzly                                               |
    | OS-EXT-SRV-ATTR:hypervisor_hostname | devstack-grizzly                                               |
    | OS-EXT-SRV-ATTR:instance_name       | instance-00000001                                              |
    | OS-EXT-STS:power_state              | 1                                                              |
    | OS-EXT-STS:task_state               | None                                                           |
    | OS-EXT-STS:vm_state                 | active                                                         |
    | accessIPv4                          |                                                                |
    | accessIPv6                          |                                                                |
    | config_drive                        |                                                                |
    | created                             | 2013-11-07T17:34:16Z                                           |
    | flavor                              | m1.small (2)                                                   |
    | hostId                              |d57e6f9f7885c615794b4d5a87103509620b6a7f567f7e7bd57e97a2        |
    | id                                  |66129319-1f1d-420d-a226-bf9fc5ea0138                            |
    | image                               | cirros-0.3.1-x86_64-uec(949c80c8-b4ac-4315-844e-69f9bef39ed1)  |
    | key_name                            | None                                                           |
    | metadata                            | {}                                                             |
    | name                                | my_instance                                                    |
    | private network                     | 10.0.0.2                                                       |
    | progress                            | 0                                                              |
    | security_groups                     | [{u'name': u'default'}]                                        |
    | status                              | ACTIVE                                                         |
    | tenant_id                           | 604bbe45ac7143a79e14f3158df67091                               |
    | updated                             | 2013-11-07T17:34:32Z                                           |
    | user_id                             | 3273a50d6cfb4a2ebc75e83cb86e1554                               |
    +-------------------------------------+----------------------------------------------------------------+
                    

The response includes the following information for the server:

+-----------------------+----------------------------------------------------+
| Name                  | Description                                        |
+=======================+====================================================+
| OS-DCF:diskConfig     | The disk configuration value, which is ``AUTO`` or |
|                       | ``MANUAL``.                                        |
+-----------------------+----------------------------------------------------+
| OS-EXT-STS:host       | Extended attribute. The host name.                 |
+-----------------------+----------------------------------------------------+
| OS-EXT-SRV-ATTR:hyper\| Extended attribute. The hypervisor host name.      |
| visor_hostname        |                                                    |
+-----------------------+----------------------------------------------------+
| OS-EXT-SRV-ATTR:insta\| Extended attribute. The instance name.             |
| nce_name              |                                                    |
+-----------------------+----------------------------------------------------+
| OS-EXT-STS:power_state| Extended attribute. The power state.               |
|                       |                                                    |
+-----------------------+----------------------------------------------------+
| OS-EXT-STS:task_state | Extended attribute. The task state.                |
|                       |                                                    |
+-----------------------+----------------------------------------------------+
| OS-EXT-STS:vm_state   | The VM state.                                      |
+-----------------------+----------------------------------------------------+
| accessIPv4            | IP v4 access address.                              |
+-----------------------+----------------------------------------------------+
| accessIPv6            | IP v6 access address.                              |
+-----------------------+----------------------------------------------------+
| created               | The date and time stamp when the server was        |
|                       | created.                                           |
+-----------------------+----------------------------------------------------+
| fault                 | The last fault issued for the server.              |
+-----------------------+----------------------------------------------------+
| flavor                | The flavor ID and links.                           |
+-----------------------+----------------------------------------------------+
| hostId                | The host ID.                                       |
+-----------------------+----------------------------------------------------+
| id                    | The server ID.                                     |
+-----------------------+----------------------------------------------------+
| image                 | The image name.                                    |
+-----------------------+----------------------------------------------------+
| metadata              | Any metadata key and value pairs.                  |
+-----------------------+----------------------------------------------------+
| name                  | The server name.                                   |
+-----------------------+----------------------------------------------------+
| status                | The server status. A status of ``ACTIVE``          |
|                       | indicates that your server built successfully and  |
|                       | is active.                                         |
+-----------------------+----------------------------------------------------+
| tenant_id             | The account number.                                |
+-----------------------+----------------------------------------------------+
| updated               | The date and time stamp when the server was last   |
|                       | updated.                                           |
+-----------------------+----------------------------------------------------+
| user_id               | The user name.                                     |
+-----------------------+----------------------------------------------------+

**Corresponding API call:** 
:rax-devdocs:`Show server details<cloud-servers/v2/developer-guide/#show-server-details>`
