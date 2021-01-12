.. _listing-virt-interfaces-with-nova:

Listing virtual interfaces (nova client)
----------------------------------------

Issue the following nova client command.

**List virtual interfaces with nova request**

.. code::

   $ nova virtual-interface-list <instance_id>

**Positional argument:**

-  ``instance_id``. The ID of the server instance for which you want to list
   virtual interfaces.

For any virtual interfaces that are connected to the specified server, the
command returns the network ID, MAC address, and IP addresses, as shown in the
following output.

**List virtual interfaces with nova response**

.. code::

   +--------------------------------------+-------------------+---------------------------------------------------------------------------------------+
   | id                                   | mac_address       | ip_addresses                                                                          |
   +--------------------------------------+-------------------+---------------------------------------------------------------------------------------+
   | 398f4189-5a60-4a5e-8a68-71e4fa014313 | 00:00:00:00:00:01 | label=private, network_id=39a43ded-7a9b-4a50-8633-e70d48363305, ip_address=172.16.0.2 |
   | d5e3c9b6-bd5d-46c9-ba7b-114df3f37fb3 | 00:00:00:00:00:00 | label=mypriv, network_id=1f7920d3-0e63-4fec-a1cb-f7916671e8eb, ip_address=10.1.0.3      |
   | d8a1baa8-3b51-4a74-9e33-f885e438a468 | 00:00:00:00:00:02 | label=public, network_id=69ebc6a6-27fc-4f47-aeca-de7c3b4685e7, ip_address=10.0.0.3    |
   +--------------------------------------+-------------------+---------------------------------------------------------------------------------------+

**Next topic:**  :ref:`Deleting a virtual interface<deleting-virt-interface>`

