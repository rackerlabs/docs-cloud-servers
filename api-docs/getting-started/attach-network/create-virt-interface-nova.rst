.. _create-virt-interface-with-nova:

Create a virtual interface (nova client)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Issue the following nova client command:

.. code::  

   $ nova virtual-interface-create <network_id> <instance_id>

**Positional arguments:**

-  ``network_id``. The ID of the network for which you want to create a virtual interface.

-  ``instance_id``. The ID of the server instance to which you want to connect the virtual 
   interface.

**Next topic:**  :ref:`List virtual interfaces for a server<list-virt-interfaces>` 