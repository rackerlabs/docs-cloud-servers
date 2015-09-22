.. _api-operations-svr-basic:

Basic server operations
~~~~~~~~~~~~~~~~~~~~~~~

This section covers the following basic server operations: 

.. include:: methods/post-create-server-servers.rst

.. BASIC OPS

.. include:: methods/post-create-server-with-disk-config-servers.rst
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

.. include:: methods/put-attach-voume-to-server-servers-server-id-os-volume-attachments.rst
.. include:: methods/get-list-servers-server-id-os-volume-attachments.rst
.. include:: methods/put-show-volume-attachment-details-servers-server-id-os-volume-attachments-attachment-id.rst
.. include:: methods/delete-delete-volume-attachment-from-server-servers-server-id-os-volume-attachments-attachment-id.rst

.. BFV OPS

.. include:: methods/post-create-bootable-volume-and-server-servers.rst

.. SERVER ACTION LOG OPS

.. include:: methods/get-retrieve-list-of-server-actions-servers-server-id-os-instance-actions.rst
.. include:: methods/get-retrieve-log-details-for-a-specified-server-action-servers-server-id-os-instance-actions-request-id.rst

.. SERVER ACTION OPS

.. include:: methods/post-change-password-for-specified-server-servers-server-id-actions.rst
.. include:: methods/post-reboot-specified-server-servers-server-id-actions.rst
.. include:: methods/post-rebuild-specified-server-servers-server-id-actions.rst
.. include:: methods/post-resize-specified-server-servers-server-id-actions.rst
.. include:: methods/post-confirm-server-resize-for-specified-server-servers-server-id-actions.rst
.. include:: methods/post-revert-server-resize-for-specified-server-servers-server-id-actions.rst
.. include:: methods/post-create-image-of-specified-server-servers-server-id-actions.rst
.. include:: methods/post-rescue-specified-server-servers-server-id-actions.rst
.. include:: methods/post-unrescue-specified-server-servers-server-id-actions.rst

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