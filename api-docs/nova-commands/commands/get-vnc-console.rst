.. _nc-get-vnc-console:

Get VNC console
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Gets a VNC console to a specified server.

**Usage:**

.. code::  

    $ nova get-vnc-console <server> <console_type>

**Positional arguments:**

-  ``server``. The name or ID of the server.

-  ``console_type``. The type of VNC console, which is ``novnc`` or ``xvpvnc``.

**Output:** Error.

**Corresponding API call:** **Corresponding API call:** 
:rax-devdocs:`Get console<cloud-servers/v2/developer-guide/#get-console>`
