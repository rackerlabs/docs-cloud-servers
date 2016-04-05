.. _nc-sa-revert-resize:

Revert resize server 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Reverts a previous resize and returns to the previous VM.

**Usage:**

.. code::  

    $ nova resize-revert <server>

**Positional argument:**

-  ``server``. The name or ID of the server that you want to revert.

**Output**: None.

**Corresponding API call:**
:rax-devdocs:`Revert server resize<cloud-servers/v2/developer-guide/#revert-server-resize-for-specified-server>`
