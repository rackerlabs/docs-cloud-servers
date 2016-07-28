.. _creating-network:

Creating network
----------------

Before you create a server, you create an isolated network that you can attach
to your new server.

To create an isolated network, you specify a name for your network and a
Classless Inter-Domain Routing (CIDR). A CIDR is a range of IP addresses used
by a network. A CIDR address looks like a normal IP address except that it ends
with a slash followed by a number. The number after the slash represents the
number of addresses in the range. For more information, see
:how-to:`CIDR Notation<using-cidr-notation-in-cloud-networks>`.

**Limitations**

-  The isolated network must exist in the same region as the Cloud Server.

-  You can create up to ten isolated networks with up to 64 servers attached to
   each one.

-  After you create an isolated network, you cannot rename it.

After you create an isolated network, copy its network ID. You use this ID to
attach the network to your server when you create your server.

**Next step:** Choose one of the following methods:

.. toctree::
   :maxdepth: 2

   creating-network-nova
   creating-network-curl