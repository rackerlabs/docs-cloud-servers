.. _nc-sa-confirm-resize:

Confirm resize server 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


Confirms a resized server. During a resize operation, the original server is saved for a 
period of time to allow roll back, in case a problem occurs. After you verify that the newly 
resized server works properly, use this operation to confirm the resize. After you confirm 
the resize, the original server is removed, and you cannot roll back to that server. All 
resizes are automatically confirmed after 24 hours, if you do not explicitly confirm or 
revert the resize.

**Usage:**

.. code::  

    $ nova resize-confirm <server>

**Positional argument:**

-  ``server``. The name or ID of the server that you want to resize.

**Output**: None.

**Corresponding API call:**
:rax-devdocs:`Confirm server resize<cloud-servers/v2/developer-guide/#confirm-server-resize-for-specified-server>`
