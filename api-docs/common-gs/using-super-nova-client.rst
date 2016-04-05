.. _using-supernova-client:

Using the supernova client
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. contents::
   :local:
   :depth: 1

The supernova client is a tool that allows you to use the nova client with multiple 
OpenStack nova environments. For more information about the supernova client, see 
https://github.com/major/supernova.

The supernova client replaces or appends environment variables to already present variables 
for the duration of the nova execution. If you have set the ``NOVA_USERNAME`` environment 
variable outside of the script, the script does not use it because the script pulls data 
from the ``~/.supernova`` configuration file and uses it to run the nova client. Additionally, 
any variables that you set before running the supernova client remain unchanged when the 
script exits.

.. _install-supernova-client:

Install the supernova client
"""""""""""""""""""""""""""""""

Before you install the supernova client on a Linux distribution or on Mac OS X, first 
:ref:`install the nova client<install-nova-client>`. 

#. Install the keyring.  For more information about the keyring, see 
   :ref:`Using the keyring<using-keyring>`.

   .. code::

      $ sudo pip install keyring
   
   .. note::

      If you previously installed the keyring, run the following command to upgrade it:

      .. code::

         $ sudo pip install --upgrade keyring
         
#. Clone and install the supernova client.

	.. code::
	
	   $ git clone https://github.com/major/supernova.git
	   $ cd supernova
	   $ sudo python setup.py install
	   
   .. note::
   
   	To uninstall the supernova client, issue the following command:
   	
   	.. code::
   	
   	   $ sudo pip uninstall supernova	
   	   
.. _set-supernova-environment-variables:

Set supernova environment variables
""""""""""""""""""""""""""""""""""""""

For supernova to work properly, set the environment variables in the supernova file in your 
user home directory.

The data in the file is exactly the same as the environment variables that you typically 
set when you run the nova client. You can copy the environment variables from your nova 
client environment into the configuration sections in the supernova file. Use nano or an 
editor of your choice to edit your supernova file:

.. code:: 

   $ nano ~/.supernova
   
The following example file shows the example environments: prodadmin, prodadminord, and 
prodadminlon.   For information about using keyrings, see 
:ref:`Using the keyring<using-keyring>`

.. code::

   [prodadmin]
   OS_AUTH_URL=https://10.24.198.11:5000/v2.0/
   NOVA_REGION_NAME=preprodinova
   NOVA_SERVICE_NAME=preprodAdminAPI
   OS_USERNAME=<my_sso_username>
   OS_PASSWORD=USE_KEYRING
   OS_TENANT_NAME=<my_sso_username>
   NOVACLIENT_INSECURE=1
 
   [prodadminord]
   OS_AUTH_URL=https://10.23.244.90:5000/v2.0/
   NOVA_REGION_NAME=ordprodadmin
   NOVA_SERVICE_NAME=ordprodadminapi
   OS_USERNAME=<my_sso_username>
   OS_PASSWORD=USE_KEYRING
   OS_TENANT_NAME=<my_sso_username>
   NOVACLIENT_INSECURE=1
 
   [prodadminlon]
   OS_AUTH_URL=https://10.21.228.61:5000/v2.0/
   NOVA_REGION_NAME=prodlon
   NOVA_SERVICE_NAME=prodlonAdminAPI
   OS_USERNAME=<my_sso_username>
   OS_PASSWORD=USE_KEYRING
   OS_TENANT_NAME=<my_sso_username>
   NOVACLIENT_INSECURE=1  
   
.. _run-supernova:

Run the supernova client
"""""""""""""""""""""""""""
   
To run the supernova client commands, use the following syntax.

.. code::

   $ supernova [--help] [--debug] [--list] [<environment>] [<command>] [<arguments>...]

**Options**

-  ``-h``, ``--help``. Shows help message and exits. Specify ``--help`` with no arguments 
   to get a listing of all nova client commands. Specify ``--help`` followed by a command 
   name to get help for a specific command.

-  ``-d``, ``--debug``. Shows nova client debug output. This option enables you to see 
   additional debug information about the requests being made to the API.

-  ``-l``, ``--list``. Lists all configured environments.

-  ``environment``. The nova environment. Specify an environment by its header name in the 
   configuration file.

-  ``command``. Nova client command.

-  ``arguments``. Nova client command arguments.

For example, to list servers in the **production** environment, run the following command.

.. code::  

   $ supernova production list 

To get details for a server instance in the **development** environment, run the following 
command.

.. code::  

   $ supernova development show 3edb6dac-5a75-486a-be1b-3b15fd5b4ab0a 

The first argument is generally the environment argument and it is expected to be a single 
word without spaces. Any text after the environment argument is passed directly to the nova 
client.