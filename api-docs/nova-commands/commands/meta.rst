.. _nc-meta:

Set or delete server metadata
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Sets or deletes metadata on a server.

**Usage:**

.. code::  

    $ nova meta <server> <action> <key>=<value> [<key>=<value> ...] 

**Positional arguments:**

-  ``server``. The name or ID of the server for which you want to set or delete metadata.

-  ``action``. Either ``set`` or ``delete``.

-  ``key``\ =\ ``action``. Metadata to set or delete. For delete, ``action`` is not required.

**Output:** None.

**Corresponding API calls:**

- :rax-devdocs:`Set server metadata item<cloud-servers/v2/developer-guide/#set-server-metadata-item>`
- :rax-devdocs:`Delete server metadata item<cloud-servers/v2/developer-guide/#delete-server-metadata-item>`
