.. _getting-network-details-with-nova:

Getting network details (nova client)
-------------------------------------

Issue the following nova client command.

**Get network details with nova request**

.. code::

   $ nova network <id>

**Positional argument:**

-  ``id``. The ID of the network for which you want to show information.

The command returns the CIDR, network ID, and label, as shown in the following
output.

**Get network details with nova response**

.. code::

   +----------+--------------------------------------+
   | Property | Value                                |
   +----------+--------------------------------------+
   | cidr     | 172.16.0.0/24                        |
   | id       | e65accc0-1d98-45eb-af76-ab3d31edc7d2 |
   | label    | new_network                          |
   +----------+--------------------------------------+

**Next topic:** :ref:`Deleting network<deleting-network>`

