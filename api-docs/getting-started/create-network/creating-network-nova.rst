.. _creating-network-with-nova:

Creating network (nova client)
------------------------------

#. Issue the following command.

   **Create network with nova request**

   .. code::

       $ nova network-create <network_label> <cidr>

   **Positional arguments:**

   -  ``network_label``. The network label, such as ``new_network``,

   -  ``cidr``. The IP block from which to allocate, such as
      ``192.168.0.0/24`` or ``2001:DB8::/64``.

   The operation returns the CIDR, ID, and label for the new network, as shown
   in the following output.

   **Create network with nova response**

   .. code::

       +----------+--------------------------------------+
       | Property | Value                                |
       +----------+--------------------------------------+
       | cidr     | 192.168.0.0/24                       |
       | id       | 1f84c238-b05a-4374-a0cb-aa6140032cd1 |
       | label    | new_network                          |
       +----------+--------------------------------------+

#. Copy the ``id`` value from the output. In this example, the ``id``
   value is ``1f84c238-b05a-4374-a0cb-aa6140032cd1``, but use the value
   returned for your network.


**Next topic:**  :ref:`Listing networks<listing-networks>`

