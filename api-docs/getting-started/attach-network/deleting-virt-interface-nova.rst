.. _deleting-virt-interface-with-nova:

Deleting a virtual interface (nova client)
------------------------------------------

Issue the following command to delete the virtual interface from your server.

**Delete a virtual interface with nova request**

.. code::

   $ nova virtual-interface-delete <instance_id> <interface_id>

**Positional arguments:**

-  ``instance_id``. The ID of the server instance from which you want to detach
   the virtual interface.

-  ``interface_id``. The ID of the virtual interface that you want to delete.

There is no operation response for a successful operation.  You will be
returned to the command prompt.