.. _nc-sa-resize:

Resize server 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Resizes a server.

**Usage:**

.. code::  

    $ nova resize [--poll] <server> <flavor>

**Positional arguments:**

-  ``server``. The name or ID of the server that you want to resize.

-  ``flavor``. The name or ID of the flavor to which you want to resize the server.

**Optional argument:**

-  ``--poll``. Blocks while the instance resizes so that progress can be reported.

**Output**: None.

**Corresponding API call:** 
:rax-devdocs:`Resize server<cloud-servers/v2/developer-guide/#resize-specified-server>`


