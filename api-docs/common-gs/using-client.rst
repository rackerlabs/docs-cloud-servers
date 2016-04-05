.. _request-using-nova-client:

Using the nova client
^^^^^^^^^^^^^^^^^^^^^^

.. contents::
   :local:
   :depth: 1

The nova client is an open-source Python client provides access to all public |apiservice| 
methods. To send requests using the client, you have to install the client and set 
environment variables.

Prerequisites
""""""""""""""""""

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
"""""""""""""""""""""""""""""

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


.. _install-services-ext:

Install the services extension
""""""""""""""""""""""""""""""""""

To use nova client commands to access the services extension, you must install the 
``novaclient`` package with the services extension, by running the following command.

.. code::  

   $ pip install rax_services_python_novaclient_ext

.. _install-virtual-int-ext:

Install the Cloud Networks virtual interface extension
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

To attach networks to existing servers, rather than just at boot time, you need to
install the virtual interface extension by using the following command:

.. code::

   $ sudo pip install os_virtual_interfacesv2_python_novaclient_ext
   
.. note::

   If you previously installed this package, run the following command to upgrade it:

   .. code::

        $ sudo pip install os_virtual_interfacesv2_python_novaclient_ext --upgrade   



.. _set-nova-environment-variables:

Set nova environment variables
"""""""""""""""""""""""""""""""""""

#. Edit your **bash.profile** file or **.bashrc** file to add and set environment
   variables that enable the heat client to connect to your Rackspace
   Cloud account. Use nano, or a text editor of your choice, to edit the file.

   .. code::

      $ nano ~/.bash_profile

#. Add the following lines to your bash profile, and save the file. Information about 
   the environment variables is provided after the example.

   .. code::
     
      export OS_AUTH_URL=https://10.24.198.11:5000/v2.0/
      export NOVA_REGION_NAME=preprodinova
      export NOVA_SERVICE_NAME=preprodAdminAPI
      export OS_USERNAME=<your_sso_username>
      export OS_PASSWORD=USE_KEYRING
      export OS_TENANT_NAME=<your_sso_username>
      export OS_TENANT_ID=<your_sso_username>
      export NOVACLIENT_INSECURE=1

   The following table describes the environment variables:

   +--------------------+--------------------------------------------------------+
   | Environment        | Description                                            |
   | Variable           |                                                        |
   +====================+========================================================+
   | NOVACLIENT_INSECURE| Set to 1. Explicitly allows the nova client to perform |
   |                    | insecure SSL (https) requests. The certificate for the |
   |                    | server is not verified against any certificate         |
   |                    | authorities. Use this option with caution.             |
   +--------------------+--------------------------------------------------------+
   | NOVA_REGION_NAME   | The region that contains the servers that you want to  |
   |                    | manipulate.                                            |
   |                    |                                                        |
   |                    | You can override the region by setting the             |
   |                    | ``--region-name`` command-line option.                 |
   |                    |                                                        |
   |                    | To help you decide which regionalized endpoint to use, |
   |                    | read about special considerations for choosing a data  |
   |                    | center at                                              |
   |                    | http://www.rackspace.com/knowledge_center/article/abou |
   |                    | t-regions.                                             |
   +--------------------+--------------------------------------------------------+
   | NOVA_SERVICE_NAME  | The Cloud service name that you want the nova client   |
   |                    | to access.                                             |
   +--------------------+--------------------------------------------------------+
   | OS_AUTH_SYSTEM     | The authentication system, which the nova client uses  |
   |                    | for authentication.                                    |
   |                    |                                                        |
   |                    | For the US Rackspace Cloud, use ``rackspace``.         |
   |                    |                                                        |
   |                    | For the UK Rackspace Cloud, use ``rackspace_uk``.      |
   +--------------------+--------------------------------------------------------+
   | OS_AUTH_URL        | The endpoint for the Rackspace Identity Service, which |
   |                    | the nova client uses for authentication.               |
   +--------------------+--------------------------------------------------------+
   | OS_NO_CACHE        | Set to 1 to **not** use the authentication token       |
   |                    | cache.                                                 |
   +--------------------+--------------------------------------------------------+
   | OS_PASSWORD        | Your SSO password.                                     |
   +--------------------+--------------------------------------------------------+
   | OS_PROJECT_ID      | Your project ID. In these examples, set it to your     |
   |                    | Rackspace Cloud account number.                        |
   +--------------------+--------------------------------------------------------+
   | OS_TENANT_NAME     | Your SSO user name.                                    |
   +--------------------+--------------------------------------------------------+
   | OS_TENANT_ID       | Your SSO user name.                                    |
   +--------------------+--------------------------------------------------------+
   | OS_USERNAME        | Your SSO user name.                                    |
   +--------------------+--------------------------------------------------------+

#. Because the bash profile contains a password, set permissions on it so other people 
   cannot read it:

   .. code::  

      $  chmod 600 ~/.bash_profile 

       
#. Be sure to source the file containing the environment variables after editing so that 
   the new settings will take effect immediately. 
   
   .. code::
   
      $ source .bash_profile

#. Run the help command to ensure that the client has installed correctly and to review 
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

.. _run-nova:

Run the nova client
""""""""""""""""""""""

To verify that you can talk to the API server, authenticate and list images:

.. code::  

   $ nova credentials 
   $ nova image-list 
       
..  note:: 

   To become familiar with the underlying API v2 request for a command, specify the 
   ``--debug`` parameter as the first parameter on any command. For example:

   .. code::  

       $ nova --debug list
       
**Troubleshooting tips**:

-  If you cannot run commands successfully, make sure that you entered your user name, 
   password, and account number correctly in the bash profile file.

-  If you change any environment variables, either log out and back in or source your bash 
   profile again.

-  To override some environment variable settings, you can use the options that are listed 
   at the end of the ``nova help`` output. For example, you can override the ``OS_PASSWORD`` 
   setting in the bash profile by specifying your password on a nova command, as follows:

   .. code::  

      $ nova --password <password> image-list 


