.. _request-using-nova-client:

Using the nova client
~~~~~~~~~~~~~~~~~~~~~

The nova client is an open-source Python client provides access to all public |apiservice| 
methods. To send requests using the client, you have to install the client and set 
environment variables.

**Prerequisites**

- Linux or Mac OS X
- Python 2.6 or later
- **setuptools** package, installed by default on Mac OS X
- **pip** package
- Rackspace Cloud account and access to |service|

+--------------------+--------------------------------------------------------+
| Prerequisite       | Description                                            |
+====================+========================================================+
| Python 2.6 or      | Currently, the nova client does not support Python 3.  |
| later              |                                                        |
+--------------------+--------------------------------------------------------+
| **setuptools**     | Installed by default on Mac OS X.                      |
| package            |                                                        |
|                    | Many Linux distributions provide packages to make      |
|                    | **setuptools** easy to install.                        |
|                    |                                                        |
|                    | Search your package manager for **setuptools** to find |
|                    | an installation package. If you cannot find one,       |
|                    | download the **setuptools** package directly from      |
|                    | http://pypi.python.org/pypi/setuptools.                |
+--------------------+--------------------------------------------------------+
| **pip** package    | To install the nova client on a Mac OS X or Linux      |
|                    | system, use **pip** because it is easy and ensures     |
|                    | that you get the latest version of the nova client     |
|                    | from the Python Package Index at                       |
|                    | http://pypi.python.org/pypi/python-novaclient/>.       |
|                    | Also, it lets you update the package later on.         |
|                    |                                                        |
|                    | Install **pip** through the package manager for your   |
|                    | system:                                                |
|                    |                                                        |
|                    | -  Mac OS X                                            |
|                    |                                                        |
|                    |    .. code::                                           |
|                    |                                                        |
|                    |        $ sudo easy_install pip                         |
|                    |                                                        |
|                    | -  Ubuntu                                              |
|                    |                                                        |
|                    |    .. code::                                           |
|                    |                                                        |
|                    |        $ aptitude install python-pip                   |
|                    |                                                        |
|                    | -  Debian                                              |
|                    |                                                        |
|                    |    .. code::                                           |
|                    |                                                        |
|                    |        $ aptitude install python-pip                   |
|                    |                                                        |
|                    | -  Fedora                                              |
|                    |                                                        |
|                    |    .. code::                                           |
|                    |                                                        |
|                    |        $ yum install python-pip                        |
|                    |                                                        |
|                    | -  CentOS, or RHEL (from EPEL or another 3rd party     |
|                    |    repository)                                         |
|                    |                                                        |
|                    |    .. code::                                           |
|                    |                                                        |
|                    |        $ yum install python-pip                        |
|                    |                                                        |
+--------------------+--------------------------------------------------------+

.. _install-nova-client:

Install the nova client
^^^^^^^^^^^^^^^^^^^^^^^^^

You install the nova client on a Linux distribution or on Mac OS X. 

.. code::

     $ sudo pip install rackspace-novaclient
     
.. note::

   If you previously installed the rackspace-novaclient package, run the following
   command to upgrade it:

   .. code::

        $ sudo pip install --upgrade rackspace-novaclient

You can specify a debug parameter on any nova command to show the underlying API request 
for the command. This is a good way to become familiar with the API requests.


If you upgrade the operating system of the desktop or remote machine where you installed 
nova, you may need to reinstall nova to ensure correct operation.

If you have trouble using pip to install the nova client, you can download a nova client 
installation package from the python package repository at http://pypi.python.org/pypi/rackspace-novaclient/,
use ``python-pip`` or ``yum`` commands instead of ``pip``.

.. _install-virtual-int-ext:

Install the Cloud networks virtual interface extension
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To attach networks to existing servers, rather than just at boot time, you need to
install the virtual interface extension by using the following command:

.. code::

   $ sudo pip install os_virtual_interfacesv2_python_novaclient_ext
   
.. note::

   If you previously installed this package, run the following command to upgrade it:

   .. code::

        $ sudo pip install os_virtual_interfacesv2_python_novaclient_ext --upgrade   

.. _set-environment-variables:

Set environment variables
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Edit your **bash.profile** file or **.bashrc** file to add and set environment
variables that enable the heat client to connect to your Rackspace
Cloud account. Use nano, or a text editor of your choice, to edit the file.

.. code::

     $ nano ~/.bash_profile

Add the following sets of lines to your bash profile and save the file.
Information about the environment variables is provided after the examples.

.. code::

     export OS_AUTH_URL=https://identity.api.rackspacecloud.com/v2.0/
     export OS_USERNAME=yourUserName
     export OS_TENANT_ID=yourTenantId
     export OS_REGION_NAME=yourRegionName
     export OS_PASSWORD=yourPassword

The following table describes the environment variables:

+-----------------------+--------------------------------------------------+
| Environment variable  | Description                                      |
+=======================+==================================================+
| OS_AUTH_URL           | The endpoint for the Rackspace Cloud Identity    |
|                       | service, which the heat client uses for          |
|                       | authentication.                                  |
+-----------------------+--------------------------------------------------+
| OS_USERNAME           | Your Rackspace Cloud user name.                  |
+-----------------------+--------------------------------------------------+
| OS_TENANT_ID          | Your Rackspace Cloud tenant ID (account number)  |
+-----------------------+--------------------------------------------------+
| OS_REGION_NAME        | The regional endpoint (for example, DFW) where   |
|                       | you want to deploy the Cloud Servers resources.  |
|                       | For details, see :ref:`service-access-endpoints`.|
+-----------------------+--------------------------------------------------+
| OS_PASSWORD           | Your Rackspace Cloud password.                   |
+-----------------------+--------------------------------------------------+

Be sure to source the file containing the environment variables after editing so that the 
new settings will take effect immediately. For example, ``source .bash_profile``.

Run the help command to ensure that the client has installed correctly and to review 
information about using the client.

.. code::

     $ nova help

To get help for a specific command, type the command name after the ``help`` parameter, 
as follows:

   .. code::  

       $ nova help <command_name> 

You cannot use every command that is listed. The nova client was written for use with 
recent development versions of OpenStack, so it includes support for some features that are 
not available in the Rackspace Cloud. For a complete list of Openstack commands, see the 
:os-docs:`OpenStack Compute command-line client reference
<cli-reference/content/novaclient_commands.html>`. 
