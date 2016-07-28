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

.. note::

   When you delete a virtual interface, the associated network is detached from
   the server instance. Also, if you want to delete an isolated network, the
   network cannot be attached to any server. Delete the virtual interface for
   the isolated network, and then you can delete the network.

API operations for virtual interfaces extension
-----------------------------------------------

For examples of these operations, see the following operations:

- :ref:`List virtual interfaces <get-retrieve-list-of-virtual-interfaces-servers-server-id-os-virtual-interfacesv2>`
- :ref:`Create virtual interfaces <post-create-virtual-interface-and-attach-to-server-servers-server-id-os-virtual-interfacesv2>`
- :ref:`Delete virtual interface <delete-delete-virtual-interface-servers-server-id-os-virtual-interfacesv2-interface-id>`
