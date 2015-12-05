.. _attach-network-intro:

Attach your network to an existing server
------------------------------------------

Use the Cloud Networks virtual interface extension to:

-  Create a virtual interface to a specified network and attach the network to an existing 
   server instance.
-  List the virtual interfaces for a server instance.
-  Delete a virtual interface and detach it from a server instance.

You can create a maximum of one virtual interface per instance per network.

These examples walk you through the steps to create a virtual interface to a specified 
network and attach the network to an existing server instance. The simple exercises show 
you how to access the Cloud Networks virtual interface extension through nova client 
commands or cURL commands.

- :ref:`Create a virtual interface<create-virt-interface>`
- :ref:`List virtual interfaces for a server<list-virt-interfaces>`
- :ref:`Delete a virtual interface from a server <delete-virt-interface>`

.. toctree::
   :maxdepth: 2

   Create a virtual interface <attach-network/create-virt-interface>
   List virtual interfaces for a server <attach-network/list-virt-interfaces>
   Delete a virtual interface from a server <attach-network/delete-virt-interface>