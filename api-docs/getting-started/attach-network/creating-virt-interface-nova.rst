.. _creating-virt-interface-with-nova:

Creating a virtual interface (nova client)
------------------------------------------

Issue the following nova client command.

**Create a virtual interface with nova request**

.. code::

   $ nova virtual-interface-create <network_id> <instance_id>

**Positional arguments:**

-  ``network_id``. The ID of the network for which you want to create a virtual
   interface.

-  ``instance_id``. The ID of the server instance to which you want to connect
   the virtual interface.

The operation returns a response, as shown in the following output.

**Create a virtual interface with nova response**

.. code::

   +--------------+------------------------------------------------------------------------------------------------+
   | Property     | Value                                                                                          |
   +--------------+------------------------------------------------------------------------------------------------+
   | id           | 045f195f-3347-487b-8e80-8ee3390eda56                                                           |
   | ip_addresses | label=added_network, network_id=1f7920d3-0e63-4fec-a1cb-f7916671e8eb, ip_address=192.168.0.1   |
   | mac_address  | FE:ED:FA:00:08:93                                                                              |
   +--------------+------------------------------------------------------------------------------------------------+

**Next topic:**  :ref:`Listing virtual interfaces for a server<listing-virt-interfaces>`