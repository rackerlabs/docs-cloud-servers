.. _deleting-network:

Deleting network
----------------

If you no longer need your network, you can delete it.

You cannot delete an isolated network until the network is detached from all
servers.

To detach a network from a server, you must delete the virtual interface or the
network from the server. Then, you can delete the network. After the network is
deleted, it no longer appears in the list of networks.

The sections are also organized by example type. To simplify your path through
this topic, decide whether you prefer neutron-client or cURL examples.

**Next step:** Choose one of the following methods:

.. toctree::
   :maxdepth: 2

   deleting-network-nova
   deleting-network-curl


