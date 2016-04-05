.. _nc-sa-rebuild:

Rebuild server 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Rebuilds a server.

**Usage:**

.. code::  

    $ nova rebuild [--rebuild_password <rebuild_password>] [--poll] <server> <image>

**Positional arguments:**

-  ``server``. The name or ID of the server that you want to rebuild.

-  ``image``. The name or ID of the image that you want to use to rebuild the server.

**Optional arguments:**

-  ``--rebuild_password``. Sets the specified password on the rebuilt instance.

-  ``--poll``. Blocks while the instance rebuilds so progress can be reported.

**Corresponding API call:** 
:rax-devdocs:`Rebuild server<cloud-servers/v2/developer-guide/#rebuild-specified-server>`
