.. _delete-virt-interface-with-nova:

Delete a virtual interface (nova client)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Issue the following command to delete the virtual interface from your server:

.. code::  

   $ nova virtual-interface-delete <instance_id> <interface_id>

**Positional arguments:**

-  ``instance_id``. The ID of the server instance from which you want to detach the 
   virtual interface.

-  ``interface_id``. The ID of the virtual interface that you want to delete.

 