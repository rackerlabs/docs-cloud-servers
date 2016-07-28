.. _deleting-server-with-nova:

Deleting server (nova client)
-----------------------------

To delete your server with the nova client, you need the server name.

Issue the following command, specifying the name of the server that you want to
delete.

**Delete a server with nova request**

   .. code::

       $ nova delete <server>

   Where ``server`` is the name or ID of the server to delete.

There is no operation response for a successful operation.  You will be
returned to the command prompt.

**Next topic:** :ref:`Create your first network<create-network-intro>`

