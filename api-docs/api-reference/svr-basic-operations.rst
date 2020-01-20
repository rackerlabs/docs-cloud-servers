.. _api-operations-svr-basic:

Server operations
~~~~~~~~~~~~~~~~~

This section covers the following basic server operations:

.. LINKS TO OPS

Basic Operations:
	- :ref:`Create server <post-create-server-servers>`
	- :ref:`Create server with disk config <post-create-server-with-disk-config-servers>`
	- :ref:`Create server with scheduler hints <post-create-server-with-sched-hint-servers>`
	- :ref:`List servers <get-retrieves-a-list-of-servers-servers>`
	- :ref:`List servers with details <get-list-servers-with-details-servers-detail>`
	- :ref:`Show server with details <get-retrieve-server-details-servers-server-id>`
	- :ref:`Update server <put-update-server-servers-server-id>`
	- :ref:`Delete server <delete-delete-server-servers-server-id>`

Key Pairs Operations:
	- :ref:`Create key pair <post-create-a-server-key-pair-os-keypairs>`
	- :ref:`Import key pair <post-import-a-server-key-pair-os-keypairs>`
	- :ref:`List key pairs <get-retrieve-list-of-key-pairs-os-keypairs>`
	- :ref:`Delete key pair <delete-delete-key-pair-os-keypairs-keypair-name>`

Volume Operations:
	- :ref:`Attach volume to server <post-attach-volume-to-server-servers-server-id-os-volume-attachments>`
	- :ref:`List volumes <get-list-servers-server-id-os-volume-attachments>`
	- :ref:`Show volume details <get-show-volume-attachment-details-servers-server-id-os-volume-attachments-attachment-id>`
	- :ref:`Detach volume from server <delete-delete-volume-attachment-from-server-servers-server-id-os-volume-attachments-attachment-id>`

Boot from Volume Operation:
	- :ref:`Create server by booting from a volume <post-create-bootable-volume-and-server-servers>`

Server Action Logs:
	- :ref:`List recent server actions <get-retrieve-list-of-server-actions-servers-server-id-os-instance-actions>`
	- :ref:`Show server action details <get-retrieve-log-details-for-a-specified-server-action-servers-server-id-os-instance-actions-request-id>`

Server Action Operations:
	- :ref:`Change password <post-change-password-for-specified-server-servers-server-id-actions>`
	- :ref:`Reset network <post-reset-network-for-specified-server-servers-server-id-actions>`
	- :ref:`Reboot server <post-reboot-specified-server-servers-server-id-actions>`
	- :ref:`Rebuild server <post-rebuild-specified-server-servers-server-id-actions>`
	- :ref:`Resize server <post-resize-specified-server-servers-server-id-actions>`
	- :ref:`Confirm server resize <post-confirm-server-resize-for-specified-server-servers-server-id-actions>`
	- :ref:`Revert server resize <post-revert-server-resize-for-specified-server-servers-server-id-actions>`
	- :ref:`Migrate server <post-migrate-server-server-id-actions>`
	- :ref:`Create image <post-create-image-of-specified-server-servers-server-id-actions>`
	- :ref:`Rescue server <post-rescue-specified-server-servers-server-id-actions>`
	- :ref:`Unrescue server <post-unrescue-specified-server-servers-server-id-actions>`
	- :ref:`Lock server <post-lock-specified-server-servers-server-id-actions>`
	- :ref:`Unlock server <post-unlock-specified-server-servers-server-id-actions>`
	- :ref:`Stop server <post-stop-specified-server-servers-server-id-actions>`
	- :ref:`Start server <post-start-specified-server-servers-server-id-actions>`

Server Address Operations:
	- :ref:`List server addresses <get-retrieves-list-of-server-addresses-servers-server-id-ips>`
	- :ref:`List server addresses with networks <get-retrieves-list-of-network-addresses-for-server-and-network-servers-server-id-ips-network-label>`

Server Metadata Operations:
	- :ref:`List server metadata items <get-list-server-metadata-servers-server-id-metadata>`
	- :ref:`Set server metadata items <put-set-server-metadata-servers-server-id-metadata>`
	- :ref:`Update server metadata items <post-updates-server-metadata-servers-server-id-metadata>`
	- :ref:`List server metadata items for a specific server <get-show-server-metadata-item-details-servers-server-id-metadata-key>`
	- :ref:`Set server metadata item for a specific server <put-set-server-metadata-item-servers-server-id-metadata-key>`
	- :ref:`Update server metadata item for a specific server <delete-delete-server-metadata-item-servers-server-id-metadata-key>`

.. INCLUDES FOR OP FILES

.. BASIC OPS

.. include:: methods/post-create-server-servers.rst
.. include:: methods/post-create-server-with-disk-config-servers.rst
.. include:: methods/post-create-server-with-sched-hint-servers.rst
.. include:: methods/get-retrieves-a-list-of-servers-servers.rst
.. include:: methods/get-list-servers-with-details-servers-detail.rst
.. include:: methods/get-retrieve-server-details-servers-server-id.rst
.. include:: methods/put-update-server-servers-server-id.rst
.. include:: methods/delete-delete-server-servers-server-id.rst


.. KEY PAIRS OPS

.. include:: methods/post-create-a-server-key-pair-os-keypairs.rst
.. include:: methods/post-import-a-server-key-pair-os-keypairs.rst
.. include:: methods/get-retrieve-list-of-key-pairs-os-keypairs.rst
.. include:: methods/delete-delete-key-pair-os-keypairs-keypair-name.rst

.. VOLUMES OPS

.. include:: methods/post-attach-volume-to-server-servers-server-id-os-volume-attachments.rst
.. include:: methods/get-list-servers-server-id-os-volume-attachments.rst
.. include:: methods/get-show-volume-attachment-details-servers-server-id-os-volume-attachments-attachment-id.rst
.. include:: methods/delete-delete-volume-attachment-from-server-servers-server-id-os-volume-attachments-attachment-id.rst

.. BFV OPS

.. include:: methods/post-create-bootable-volume-and-server-servers.rst

.. SERVER ACTION LOG OPS

.. include:: methods/get-retrieve-list-of-server-actions-servers-server-id-os-instance-actions.rst
.. include:: methods/get-retrieve-log-details-for-a-specified-server-action-servers-server-id-os-instance-actions-request-id.rst

.. SERVER ACTION OPS

.. include:: methods/post-change-password-for-specified-server-servers-server-id-actions.rst
.. include:: methods/post-reset-network-for-specified-server-servers-server-id-actions.rst
.. include:: methods/post-reboot-specified-server-servers-server-id-actions.rst
.. include:: methods/post-rebuild-specified-server-servers-server-id-actions.rst
.. include:: methods/post-resize-specified-server-servers-server-id-actions.rst
.. include:: methods/post-confirm-server-resize-for-specified-server-servers-server-id-actions.rst
.. include:: methods/post-revert-server-resize-for-specified-server-servers-server-id-actions.rst
.. include:: methods/post-migrate-server-server-id-actions.rst
.. include:: methods/post-create-image-of-specified-server-servers-server-id-actions.rst
.. include:: methods/post-rescue-specified-server-servers-server-id-actions.rst
.. include:: methods/post-unrescue-specified-server-servers-server-id-actions.rst
.. include:: methods/post-lock-specified-server-servers-server-id-actions.rst
.. include:: methods/post-unlock-specified-server-servers-server-id-actions.rst
.. include:: methods/post-start-specified-server-servers-server-id-actions.rst
.. include:: methods/post-stop-specified-server-servers-server-id-actions.rst

.. SERVER ADDRESS OPS

.. include:: methods/get-retrieves-list-of-server-addresses-servers-server-id-ips.rst
.. include:: methods/get-retrieves-list-of-network-addresses-for-server-and-network-servers-server-id-ips-network-label.rst

.. SERVER METADATA OPS

.. include:: methods/get-list-server-metadata-servers-server-id-metadata.rst
.. include:: methods/put-set-server-metadata-servers-server-id-metadata.rst
.. include:: methods/post-updates-server-metadata-servers-server-id-metadata.rst
.. include:: methods/get-show-server-metadata-item-details-servers-server-id-metadata-key.rst
.. include:: methods/put-set-server-metadata-item-servers-server-id-metadata-key.rst
.. include:: methods/delete-delete-server-metadata-item-servers-server-id-metadata-key.rst
