.. _server-actions-extension:

========================
Server Actions Extension
========================

The server actions extension allows you to view a log of events and actions
taken on a server. First, execute a
``GET $endpoint/servers/{server-id}/os-instance-actions`` to see a list of the
actions, then you can show more details of a specific event by using
``GET $endpoint/servers/{server-id}/os-instance-actions/{request-id}``.

List server actions and show action details operations
------------------------------------------------------

For examples of these operations, see the following operations:

- :ref:`Change password for specified server <post-change-password-for-specified-server-servers-server-id-actions>`
- :ref:`Resize specified server <post-resize-specified-server-servers-server-id-actions>`
- :ref:`Confirm server resize <post-confirm-server-resize-for-specified-server-servers-server-id-actions>`
- :ref:`Revert server resize <post-revert-server-resize-for-specified-server-servers-server-id-actions>`
- :ref:`Reboot server <post-reboot-specified-server-servers-server-id-actions>`
- :ref:`Rebuild server <post-rebuild-specified-server-servers-server-id-actions>`
- :ref:`Create image <post-create-image-of-specified-server-servers-server-id-actions>`
- :ref:`Rescue server <post-rescue-specified-server-servers-server-id-actions>`
- :ref:`Unrescue server <post-unrescue-specified-server-servers-server-id-actions>`