.. _nc-sa-change-password:

Change root password 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Changes the root password for a server. The command prompts you for the new password.

**Usage:**

.. code::  

    $ nova root-password <server>

**Positional argument:**

-  ``server``. The name or ID of the server for which you want to change the root password.

**Output**: The command prompts you for the new password twice:

.. code::  

    New password: 
    Again: 

**Corresponding API call:** 
:rax-devdocs:`Change root password<cloud-servers/v2/developer-guide/#change-password-for-specified-server>`

