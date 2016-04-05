.. _nc-sa-reboot-server:

Reboot server 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Reboots a server.

**Usage:**

.. code::  

    $ nova reboot [--hard] [--poll] <server>

**Positional argument:**

-  ``server``. The name or ID of the server that you want to reboot.

**Optional arguments:**

-  **--hard**. Performs a hard reboot. A soft reboot is the default.

-  **--poll**. Blocks while the instance reboots so progress can be reported.

**Output:** None.

**Corresponding API call:** 
:rax-devdocs:`Reboot server<cloud-servers/v2/developer-guide/#reboot-specified-server>`
