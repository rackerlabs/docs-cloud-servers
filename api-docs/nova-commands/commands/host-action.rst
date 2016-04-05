.. _nc-host-action:

Perform host actions 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Performs the specified power action on a specified host.

**Usage:**

.. code::  

    $ nova host-action [--action <action>] <hostname> 

**Positional argument:**

-  ``hostname``. The name of the host machine.

**Optional argument:**

-  ``--action`` ``action``. A power action: ``startup``, ``reboot``, or ``shutdown``.

**Output:** Error.
