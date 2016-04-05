.. _nc-delete-server:

Delete a server
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Deletes a server.

**Usage:**

.. code::  

    $ nova delete <server>

**Positional argument:**

-  ``server``. The name or ID of the server that you want to delete.

**Output:** None.

Issue the following command to list servers to determine whether a server was deleted. 
After a server is deleted, it no longer appears in the list of servers.

.. code::  

    $ nova list

It might take a few minutes for a server to be deleted.

**Corresponding API call:** `Delete
Server <http://docs.rackspace.com/servers/api/v2/cs-devguide/content/Delete_Server-d1e2883.html>`__.
