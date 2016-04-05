.. _nc-sa-rescue:

Rescue server 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Rescues a server.

**Usage:**

.. code::  

    $ nova rescue <server>

**Positional argument:**

-  ``server``. The name or ID of the server that you want to rescue.

**Output**:

.. code::  

    +-----------+--------------+
    | Property  | Value        |
    +-----------+--------------+
    | adminPass | RmQ5s48RwDxm |
    +-----------+--------------+

**Corresponding API call:** 
:rax-devdocs:`Rescue server<cloud-servers/v2/developer-guide/#rescue-specified-server>`
