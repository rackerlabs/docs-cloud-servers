==============
API extensions
==============

API extensions introduction
---------------------------

Rackspace has implemented several Cloud servers extensions, which provide either new 
functionality or enhanced functionality for existing operations. You can list 
available extensions and get details for a specific extension.

Extended responses and actions
------------------------------

Use extensions to define new data types, parameters, actions, headers,
states, and resources.


.. important::
   Applications should be prepared to ignore response data that
   contains extension elements. An extended state should always be treated as
   an ``UNKNOWN`` state if the application does not support the extension.
   Applications should also verify that an extension is available before
   submitting an extended request.


Extensions API operations
-------------------------

Using API operations, users and applications can programmatically determine which extensions 
are available, either by listing them or getting details for a specific extension.

For examples of these operations, see :ref:`Extension operations <api-operations-svr-misc>`.

Extensions
----------

.. toctree::
   :maxdepth: 2

   ext-rackspace-extensions
   ext-disk-configuration
   ext-extended-status
   ext-rescue-mode
   ext-used-limits
   ext-scheduled-images
   ext-flavors-extra-specs
   ext-flavors-os-extra-specs
   ext-server-actions
   ext-config-drive
   ext-volumes
   ext-boot-from-volume
   ext-network
   ext-virtual-interface