====================
Rackspace Extensions
====================

Using API operations, users and applications can programmatically determine
which extensions are available, either by listing them or getting details for a
specific extension. To get the list of currently available extensions, see
:ref:`Retrieve list of extensions <get-retrieve-list-of-extensions-extensions>`.

At this time, Rackspace provides the following extensions to the
|product name|:

-  **Disk configuration extension**. Enables control of how the disk is
   partitioned when a server is created, rebuilt, or resized.
   See :ref:`Disk configuration extension <disk-configuration-extension>`.

-  **Extended status extension**. Shows extended statuses including the
   VM, task, and power statuses in the response bodies for the list server
   and get server details calls.
   See :ref:`Extended status extension <extended-status-extension>`.

-  **Rescue mode extension**. Creates a new server with the file system
   for the specified version of Cloud Servers mounted to fix file system
   and configuration errors.
   See :ref:`Rescue mode extension <rescue-mode-extension>`.

-  **Used limits extension**. Returns the amount of absolute limit
   capacity that is currently used.
   See :ref:`Used limits extension <used-limits-extension>`.

-  **Volume attachment extension**. In conjunction with the Cloud Block
   Storage API, you can attach a volume to a server instance, list
   volume attachments for a server instance, get volume details for a
   volume attachment, and delete a volume attachment.
   See :ref:`Volume attachment extension <volumes-extension>`.

-  **Scheduled images**. Allows you to schedule automatic creation of
   server images.
   See :ref:`Scheduled images extension <scheduled-images-extension>`.

-  **Flavor extra specs**. Allows you to list, create, and update the
   extra-specs or keys for a flavor.
   See :ref:`Flavor extra specs extension <flavors-extra-specs-extension>`.

-  **Flavor OS extra specs**. Provides the
   ``OS-FLV-WITH-EXT-SPECS:extra_specs`` attribute for flavor listings, using
   the additional os-extra_specs URI request parameter. See
   :ref:`Flavor OS extra specs extension <flavors-os-extra-specs-extension>`.

-  **OS server actions**. allows you to view a log of events and
   actions taken on a server. See
   :ref:`Server actions log extension <server-actions-extension>`.

-  **Config drive**. read-only configuration drive that is attached to
   server instances on boot. See
   :ref:`Config drive extension <config-drive-extension>`.

-  **Boot from volume**. Shows you extra specifications for a flavor. See
   :ref:`Boot from volume extension <boot-from-volume-extension>`.

-  **Networks**. Shows you how to attach and manage networks. See
   :ref:`Networking extension <networks-extension>`.

-  **Virtual Interfaces**. Shows you how to manage virtual interfaces for
   networks. See
   :ref:`Virtual interface extension <virtual-interfaces-extension>`.

-  **Scheduler Hints**. Allows you to specify whether you want to build a new
   server near to, or far fram, an existing server. See
   :ref:`Scheduler hint extension <scheduler-hint-extension>`.

