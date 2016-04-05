.. _nc-get-image-details:

Get image details
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


Shows details for a specified image.

**Usage:**

.. code::  

    $ nova image-show <image>

**Positional argument:**

-  ``image``. The name or ID of the image for which you want to show details.

**Output:**

.. code::  

    +------------------------------------------------+--------------------------------------+
    | Property                                       | Value                                |
    +------------------------------------------------+--------------------------------------+
    | OS-DCF:diskConfig                              | AUTO                                 |
    | created                                        | 2012-02-28T19:40:46Z                 |
    | id                                             | 03318d19-b6e6-4092-9b5c-4758ee0ada60 |
    | metadata arch                                  | x86-64                               |
    | metadata auto_disk_config                      | True                                 |
    | metadata com.rackspace__1__build_core          | 1                                    |
    | metadata com.rackspace__1__build_managed       | 1                                    |
    | metadata com.rackspace__1__build_rackconnect   | 1                                    |
    | metadata com.rackspace__1__options             | 0                                    |
    | metadata com.rackspace__1__visible_core        | 1                                    |
    | metadata com.rackspace__1__visible_managed     | 1                                    |
    | metadata com.rackspace__1__visible_rackconnect | 1                                    |
    | metadata image_type                            | base                                 |
    | metadata org.openstack__1__architecture        | x64                                  |
    | metadata org.openstack__1__os_distro           | org.centos                           |
    | metadata org.openstack__1__os_version          | 5.6                                  |
    | metadata os_distro                             | centos                               |
    | metadata os_type                               | linux                                |
    | metadata os_version                            | 5.6                                  |
    | metadata rax_managed                           | false                                |
    | metadata rax_options                           | 0                                    |
    | minDisk                                        | 10                                   |
    | minRam                                         | 256                                  |
    | name                                           | CentOS 5.6                           |
    | progress                                       | 100                                  |
    | status                                         | ACTIVE                               |
    | updated                                        | 2012-05-17T17:14:17Z                 |
    +------------------------------------------------+--------------------------------------+

**Corresponding API call:** 
:rax-devdocs:`Get image details<cloud-servers/v2/developer-guide/#retrieve-image-details>`
