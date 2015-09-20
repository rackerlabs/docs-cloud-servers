.. _virtual-interfaces-extension:

============================
Virtual Interfaces extension
============================

A virtual interface works in the same way as the network interface card
(NIC) inside your laptop. Like a NIC, a virtual interface is the medium
through which you can attach a network. To use a virtual interface to
attach a network to your server, you create and connect a virtual
interface for a specified network to a server instance. The network,
which is comprised of logical switches, is attached to your server
instance through the virtual interface.

You can create a maximum of one virtual interface per instance per
network.

You can use the virtual interface extension to:

*  List the virtual interfaces for a server instance.

*  Create a virtual interface.

*  Delete a virtual interface for a network from a server instance. When
   you delete a virtual interface, the associated network is detached
   from the server instance.

..note:: If you want to delete an isolated network, the network cannot be
   attached to any server. Delete the virtual interface for the isolated
   network, and then you can delete the network.

API operations for virtual interfaces extension 
-----------------------------------------------

For examples of these operations, see :ref:`Virtual interface operations <api-operations-networks>` .



