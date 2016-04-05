==================================================================================================================
Reset Instance Extension Overview - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
==================================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  Reset Instance Extension Overview
   :name: reset-instance-extension-overview
   :class: title

A server instance, which is a virtual machine (VM), can get into a state
where you cannot delete or manipulate it, but it is still counted
against the quota for a project.

The reset state extension, an extension to the OpenStack API v1.1,
enables you to reset the state of a server instance. You can reset the
state of an instance to ERROR state so that you can delete it.

You can use this extension through the API directly or through the Nova
client. To use this extension through the nova client, you must install
the nova client.

The reset state extension is implemented as a new ``os-resetState``
action on an instance. This action takes a single required argument,
``state``, which can have one of the following values:

-  ``error``. Places the instance in ERROR state, which enables you to
   delete the instance. The default state for a reset operation is the
   ERROR state.

-  ``active``. Places the instance in ACTIVE state.

Currently, no other states are available for this operation.

The ``vm_state`` of the instance is restored to the ERROR or ACTIVE
state, respectively, and the ``task_state`` is cleared.

To install the nova client, see
`*Prerequisites* <nova_client_install_overview.html>`__.

To use the API directly, go to `the section called “Reset State
” <section_reset_api_usage.html>`__.
