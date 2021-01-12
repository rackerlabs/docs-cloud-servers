.. _attach-network-intro:

=========================================
Attach your network to an existing server
=========================================

Use the Cloud Networks virtual interface extension to:

-  Create a virtual interface to a specified network and attach the network to
   an existing server instance.
-  List the virtual interfaces for a server instance.
-  Delete a virtual interface and detach it from a server instance.

You can create a maximum of one virtual interface per instance per network.

These examples walk you through the steps to create a virtual interface to a
specified network and attach the network to an existing server instance. The
examples show you how to access the Cloud Networks virtual interface extension
through nova client commands or cURL commands.

.. toctree::
   :maxdepth: 2

   Creating a virtual interface <attach-network/creating-virt-interface>
   Listing virtual interfaces for a server <attach-network/listing-virt-interfaces>
   Deleting a virtual interface from a server <attach-network/deleting-virt-interface>