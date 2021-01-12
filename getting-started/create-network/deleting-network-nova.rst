.. _deleting-network-with-nova:

Deleting network (nova client)
------------------------------

#. Issue the following command to delete the virtual interface from your
   server.

   **Delete virtual interface with nova request**

   .. code::

       $ nova virtual-interface-delete <instance_id> <interface_id>

   **Positional arguments:**

   -  ``instance_id``. The ID of the server instance from which you want to
      detach the virtual interface.

   -  ``interface_id``. The ID of the virtual interface that you want to
      delete.

   There is no operation response for a successful operation.  You will be
   returned to the command prompt.

#. Issue the following nova client command to delete the network.

   **Delete network with nova request**

   .. code::

       $ nova network-delete <id>

   **Positional argument:**

   -  ``id``. The network ID of the network that you want to delete.

   There is no operation response for a successful operation.  You will be
   returned to the command prompt.

**Next topic:**  :ref:`Attach your network to an existing server<attach-network-intro>`