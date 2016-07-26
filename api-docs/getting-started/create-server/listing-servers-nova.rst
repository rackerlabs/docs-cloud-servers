.. _listing-servers-with-nova:

Listing servers (nova client)
-----------------------------

#. Issue the following command.

   **List servers with nova request**

   .. code::

       $ nova list

   For each server, the command returns the server ID, name, status, and
   addresses for any attached networks, as shown in the following output.

   **List servers with nova response**

   .. code::

       +--------------------------------------+----------------+--------+---------------------------------------------------------------------------------------+
       | ID                                   | Name           | Status | Networks                                                                              |
       +--------------------------------------+----------------+--------+---------------------------------------------------------------------------------------+
       | 9da98125-0de8-4b84-880c-b42977c32773 | myUbuntuServer | ACTIVE | public=2001:4800:780d:0509:d87b:9cbc:ff04:488b, 198.101.231.59; private=10.179.224.74 |
       | a09e7493-7429-41e1-8d3f-384d7ece09c0 | UbuntuDevStack | ACTIVE | public=2001:4800:780e:0510:d87b:9cbc:ff04:3e81, 50.56.186.185; private=10.180.13.75   |
       +--------------------------------------+----------------+--------+---------------------------------------------------------------------------------------+

   The networks include any isolated networks that you have created and
   Rackspace public and private networks.

#. Look for the server you just created in the list of servers. Servers are
   listed by server ID.

**Next topic:** :ref:`Deleting server<deleting-server>`

