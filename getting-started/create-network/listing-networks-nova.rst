.. _listing-networks-with-nova:

Listing networks (nova client)
------------------------------

Issue the following nova client command.

**List networks with nova request**

.. code::

   $ nova network-list

For each network, the command returns the network ID, label, and CIDR, as shown
in the following output.

**List networks with nova response**

.. code::

   +--------------------------------------+-------------+----------------+
   | ID                                   | Label       | CIDR           |
   +--------------------------------------+-------------+----------------+
   | 00000000-0000-0000-0000-000000000000 | public      |                |
   | 11111111-1111-1111-1111-111111111111 | private     |                |
   | 1f84c238-b05a-4374-a0cb-aa6140032cd1 | new_network | 192.168.0.0/24 |
   +--------------------------------------+-------------+----------------+

In the network list, ServiceNet is labeled as ``private``, and PublicNet is
labeled as ``public``.

**Next topic:**  :ref:`Booting server<booting-server-with-net>`

