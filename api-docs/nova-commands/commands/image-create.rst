.. _nc-sa-create-image:

Create image
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Creates a new image by taking a snapshot of a running server.

**Usage:**

.. code::  

    $ nova image-create [--poll] <server> <name>

**Positional arguments:**

-  ``server``. The name or ID of the server from which you want to create an image.

-  ``name``. The name of the snapshot.

**Optional argument:**

-  ``--poll``. Blocks while the snapshot builds so progress can be reported.

**Output:** The following error, though the command actually works.

.. code::  

    ERROR: The server has either erred or is incapable of performing the requested operation.
    (HTTP 500) (Request-ID: req-d7288752-7c6b-4f28-85e3-74eae8163a68)

**Corresponding API call:** 
:rax-devdocs:`Create image<cloud-servers/v2/developer-guide/#create-image-of-specified-server>`