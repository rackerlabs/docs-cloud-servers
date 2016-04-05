.. _nc-update-host:

Update host 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Updates settings for a specified host.

**Usage:**

.. code::  

    $ nova host-update [--status <status>] [--maintenance <maintenance_mode> <hostname>

**Positional argument:**

-  ``hostname``. The name of the host machine.

**Optional arguments:**

-  ``--status`` ``status``. Either enable or disable a host.

-  ``--maintenance`` ``maintenance_mode``. Either put host to or resume host from 
   maintenance.
