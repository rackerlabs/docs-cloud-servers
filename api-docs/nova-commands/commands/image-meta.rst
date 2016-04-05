.. _nc-image-meta:

Set or delete image metadata
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Sets or deletes metadata on a server.

**Usage:**

.. code::  

    $ nova image-meta <image> <action> <key>=<value> [<key>=<value> ...] 

**Positional arguments:**

-  ``image``. The name or ID of the image for which you want to set or delete metadata.

-  ``action``. Either ``set`` or ``delete``.

-  ``key``\ =\ ``action``. Metadata to set or delete. For delete, ``action`` is not required.

**Output:** None.

**Corresponding API calls:**

- :rax-devdocs:`Set image metadata item<cloud-servers/v2/developer-guide/#set-image-metadata-item-for-specified-image>`
- :rax-devdocs:`Delete image metadata item<cloud-servers/v2/developer-guide/#delete-image-metadata-item-for-specified-image>` 