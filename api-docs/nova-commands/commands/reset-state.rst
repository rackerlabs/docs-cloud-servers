.. _nc-sa-reset-state:

Reset server state
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Resets the state of an instance. By default, the command resets the VM to the ``ERROR`` 
state, which enables you to delete it.

.. code::  

    nova reset-state [--active] <server>

**Positional argument:**

-  ``server``. The name or ID of server.

**Optional argument:**

-  ``--active``. This option resets the instance to the ACTIVE state rather than ERROR 
   state.

**Output:** None.

**Corresponding API call:** 

.. COMMENT `the section called “Reset State” <section_reset_api_usage.html>`__.
