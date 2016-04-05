.. _nc-boot-server:

Boot a server
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Creates and boots a server.

**Usage:**

.. code::  

    $ nova boot <name> --flavor <flavor> --image <image>

**Positional argument:**

-  ``name``. The name of the server.

**Optional arguments:**

-  ``--no-service-net``. Optional. Opts out of attaching to the servicenet network.

   This parameter is mutually exclusive with the ``--no-public`` parameter. If you specify
   both the ``--no-public`` and ``--no-service-net`` parameters, both parameters are ignored.

   For example, to opt out of attaching to the servicenet network, issue the following 
   command:

   .. code::  

       $ nova boot <name> --flavor <flavor> --image <image> --nic net-id=<private-net-uuid> --no-service-net

-  ``--no-public``. Optional. Opts out of attaching to the public network.

   This parameter is mutually exclusive with the ``--no-service-net`` parameter. If you 
   specify both the ``--no-public`` and ``--no-service-net`` parameters, both parameters 
   are ignored.

   For example, to opt out of attaching to the public network, issue the following command:

   .. code::  

       $ nova boot <name> --flavor <flavor> --image <image> --nic net-id=<private-net-uuid> --no-public

-  ``--disk-config`` {``auto``|``manual``}. Specifies whether to expand the primary 
   partition to fill the disk. This value overrides the value inherited from image.

-  **--flavor** ``flavor``. Required. The flavor ID for the new server. To get a list of 
   flavors, issue **nova flavor-list**.

-  **--image** ``image``. Required. The image ID for the new server. To get a list of 
   images, issue **nova image-list**.

-  **--meta** ``key``=``value``. Arbitrary key and value metadata that is written to 
   ``/meta.js`` on the new server. Multiple metadata key pairs can be specified.

-  **--file** ``dst-path``=``src-path``. Stores arbitrary files from ``src-path`` 
   locally to ``dst-path`` on the new server. You can store up to five files.

-  **--key_name** ``key_name``. Key name of key pair. First, create the key pair with the 
   **keypair-add** command.

-  **--user_data** ``user-data``. User data file, which is exposed by the metadata server.

-  **--availability_zone** ``availability-zone``. The availability zone for instance 
   placement.

-  **--security_groups** ``security_groups``. A comma-separated list of security group names.

-  **--block_device_mapping** ``dev_name=mapping``. Block device mapping in the format:

   .. code::  

       dev_name=id:type:size(GB):delete_on_terminate

-  **--hint** ``key``=``value``. Arbitrary key and value pairs that are sent to the 
   scheduler for custom use.

-  **--nic** net-id=``private-net-id``, v4-fixed-ip=``ip-addr``. Creates a NIC 
   on the server. Specify this option multiple times to create multiple NICs. 
   
   Optionally, to attach a NIC with a specified UUID to a network, specify the ``net-id``=
   ``private-net-id`` parameter. This parameter attaches your server to the public and 
   servicenet networks in addition to attaching to your private tenant network.

   Optionally, specify the ``v4-fixed-ip``=``ip-addr`` option to specify an IPv4 fixed 
   address for NIC.

-  **--config-drive** ``value``. Enables a configuration drive.

-  **--poll**. Blocks while the instance builds so progress can be reported.

-  **--key-name** ``myKey``. The name or ID of the key.

**Output:**

.. code::  

    +-------------------------+--------------------------------------+
    | Property                | Value                                |
    +-------------------------+--------------------------------------+
    | OS-DCF:diskConfig       | AUTO                                 |
    | accessIPv4              |                                      |
    | accessIPv6              |                                      |
    | adminPass               | SkRokc8RWRWy                         |
    | created                 | 2012-08-15T19:57:26Z                 |
    | flavor                  | 512MB Standard Instance              |
    | hostId                  |                                      |
    | id                      | 1e73c9fc-9a05-49c4-adf4-7c00b08add1e |
    | image                   | CentOS 5.6                           |
    | metadata                | {}                                   |
    | name                    | centos-diane                         |
    | progress                | 0                                    |
    | status                  | BUILD                                |
    | tenant_id               | 010101                               |
    | updated                 | 2012-08-15T19:57:27Z                 |
    | user_id                 | 170454                               |
    +-------------------------+--------------------------------------+

The command lists the following information:

+----------------+-----------------------------------------------------------+
| Name           | Description                                               |
+================+===========================================================+
| OS-DCF:diskCon\| The disk configuration value, which is ``AUTO`` or        |
| fig            | ``MANUAL``. See `Rackspace                                |
|                | Extensions <http://docs.rackspace.com/servers/api/v2/cs-d |
|                | evguide/content/ch_extensions.html>`__.                   |
+----------------+-----------------------------------------------------------+
| adminPass      | The administrative password that you use to access the    |
|                | server.                                                   |
+----------------+-----------------------------------------------------------+
| created        | The date and time when the server was created.            |
+----------------+-----------------------------------------------------------+
| flavor         | The flavor ID. See `List                                  |
|                | Flavors <http://docs.rackspace.com/servers/api/v2/cs-devg |
|                | uide/content/List_Flavors-d1e4188.html>`__.               |
+----------------+-----------------------------------------------------------+
| hostId         | The host ID.                                              |
+----------------+-----------------------------------------------------------+
| id             | The server ID.                                            |
+----------------+-----------------------------------------------------------+
| image          | The image ID. For a list of images, see `List             |
|                | Images <http://docs.rackspace.com/servers/api/v2/cs-devgu |
|                | ide/content/List_Images-d1e4435.html>`__.                 |
+----------------+-----------------------------------------------------------+
| metadata       | Metadata key and value pairs.                             |
+----------------+-----------------------------------------------------------+
| name           | The server name.                                          |
|                |                                                           |
|                | The name that you specify in a create request becomes the |
|                | initial host name of the server. After the server is      |
|                | built, if you change the server name in the API or change |
|                | the host name directly, the names are not kept in sync.   |
|                |                                                           |
|                | Also, server names are not guaranteed to be unique.       |
+----------------+-----------------------------------------------------------+
| progress       | A percentage value from 0 to 100 that represents the      |
|                | progress of the build.                                    |
+----------------+-----------------------------------------------------------+
| tenant_id      | The account ID.                                           |
+----------------+-----------------------------------------------------------+
| updated        | The date and time that the server was last updated.       |
+----------------+-----------------------------------------------------------+
| user_id        | The user ID.                                              |
+----------------+-----------------------------------------------------------+

**Corresponding API call:** 
:rax-devdocs:`Create server<cloud-servers/v2/developer-guide/#create-server>`
