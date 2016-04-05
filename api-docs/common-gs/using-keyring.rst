.. _using-keyring:

Using the keyring
^^^^^^^^^^^^^^^^^^^

.. contents::
   :local:
   :depth: 1


Due to security policies, you might not want to store API keys or passwords in the plain 
text supernova configuration file. You can now store any configuration value within the 
keychain for your operating system. This function, which is available through the 
`keyring <https://https://pypi.python.org/pypi/keyring>`__ module, has been tested on the 
following platforms:

- **Mac**: Keychain Access.app
- **Linux**: gnome-keyring, kwallet

To get started, choose an environment and a configuration option. The following example 
shows some data that you might not want to store in plain text:

.. code::

   $ supernova-keyring --set production NOVA_API_KEY
   
.. tip::

   If you need to use the same data for multiple environments, you can use a global 
   credential item very easily: 
   
   .. code::
   
      $ supernova-keyring --set global MyCompanyLDAPPassword
      
After you store the data, test a retrieval, by using one of the following commands:

.. code::

   # Normal, per-environment storage 
   $ supernova-keyring --get production NOVA_API_KEY   
   
   # Global storage 
   $ supernova-keyring --get global MyCompanyLDAPPassword
   
Confirm that you want the data from your keychain displayed in plain text.

After you store your sensitive data, simply adjust your supernova configuration file:

.. code::

   # NOVA_API_KEY = really_sensitive_api_key_here  
   # If using storage per environment
   NOVA_API_KEY=USE_KEYRING  
 
   # If using global storage 
   NOVA_API_KEY=USE_KEYRING['MyCompanyLDAPPassword']
   
When the supernova client reads your configuration file and spots a value of ``USE_KEYRING``, 
it automatically looks for credentials stored in the ``NOVA_API_KEY`` environment variable 
for that environment. If your keyring does not have a corresponding credential, you receive 
an exception.
