.. _scheduler-hint-extension:

========================
Scheduler Hint Extension
========================

A Scheduler Hint allows a cloud server to be built near to, or far from, an
existing server within a specific zone. If a build request with a hint can not
be satisfied then the build will not succeed, and the server, which will have a
status of ``ERROR`` and a task state of ``scheduling``, must be manually
deleted.

A zone is a logical container for servers. The Public IP Zone is the zone in
which a Public IP can be shared between two or more servers.

.. note:
   A Public IP Zone will contain servers that are all made up of the same
   flavor class. For example a General Purpose - 1 server will never share a
   Public IP Zone with a Memory - 1 server.

Why use scheduler hints?
-------------------------

The following use cases identify some reasons you might use scheduler hints:

- **Reduce server density** - You may have two or more VM's on the same
  physical host. By specifying the ``far`` parameter, you may mitigate risk.

- **Mitigate impact of maintenances** - If Rackspace needs to reboot all
  servers for maintenance, specifying the ``far`` parameter, helps to ensure
  that all servers aren't affected at once.

- **Build servers in the same 'Public IP zone' (cell)** - In order to share an
  IP between two servers they need to be in the same Cell, by specifying the
  ``near`` parameter.

- **Build servers to achieve lowest latency**: If you have certain applications
  that are sensitive to latency and want to build components of those as close
  to one another as possible, specify the ``near`` parameter. This might lower
  availability.

- **Build servers to achieve higher availability**: If you need to ensure parts
  of your application are as far away from each other as possible, specify the
  ``far`` parameter. This might increase latency.

Scheduler hint operations
--------------------------------------------

For an example of this operation, see
:ref:`Create server with scheduler hint <post-create-server-with-sched-hint-servers>`.

