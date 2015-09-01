Server operations
---------------------

This section describes the API operations for servers.

.. toctree::
    :maxdepth: 2

    [BASIC] Create server <post-create-server-servers>
    [BASIC] List servers <get-retrives-a-list-of-servers-servers>
    [BASIC] List servers with details <get-list-servers-with-details-servers-detail>
    [BASIC] Show details for server <get-retrieve-server-details-servers-server-id>
    [BASIC] Update server <put-update-server-servers-server-id>
    [BASIC] Delete server <delete-delete-server-servers-server-id>
    
    [SERVER ADDRESS] List server's IP addresses <get-retrieves-list-of-server-addresses-servers-server-id-ips>
    [SERVER ADDRESS] List server's IP addresses for a network <get-retrieves-list-of-network-addresses-for-server-and-network-servers-server-id-ips-network-label>
    
    [SERVER ACTIONS] Change password <post-change-password-for-specified-server-servers-server-id-actions>
    [SERVER ACTIONS] Reboot server <post-reboot-specified-server-servers-server-id-actions>
    [SERVER ACTIONS] Rebuild server <post-rebuild-specified-server-servers-server-id-actions>
    [SERVER ACTIONS] Resize server <post-resize-specified-server-servers-server-id-actions>
    [SERVER ACTIONS] Confirm resize server <post-confirm-server-resize-for-specified-server-servers-server-id-actions>
	[SERVER ACTIONS] Revert resize server <post-revert-server-resize-for-specified-server-servers-server-id-actions>
	[SERVER ACTIONS] Rescue server <post-rescue-specified-server-servers-server-id-actions>
	[SERVER ACTIONS] Unrescue server <post-unrescue-specified-server-servers-server-id-actions>
	[SERVER ACTIONS] Create server image<post-create-image-of-specified-server-servers-server-id-actions>
    
    [SERVER META] Show all metadata for a server <get-list-server-metadata-servers-server-id-metadata>
    [SERVER META] Create or replace all metadata for a server <put-set-server-metadata-servers-server-id-metadata>
    [SERVER META] Update all metadata for a server <post-updates-server-metadata-servers-server-id-metadata>
    [SERVER META] Show metadata item by key <get-show-server-metadata-item-details-servers-server-id-metadata-key>
    [SERVER META] Create or replace metadata item by key <put-set-server-metadata-item-servers-server-id-metadata-key>
    [SERVER META] Delete metadata item by key <delete-delete-server-metadata-item-servers-server-id-metadata-key>
    
    [VOLUME] Attach volume <put-attach-voume-to-server-servers-server-id-os-volume-attachments>
    [VOLUME] List volumes for server <get-list-server-metadata-servers-server-id-os-volume-attachments>
    [VOLUME] Show volume details <put-show-volume-attachment-details-servers-server-id-os-volume-attachments-attachment-id>
    [VOLUME] Delete volume from server <delete-delete-volume-attachment-from-server-servers-server-id-os-volume-attachments-attachment-id>
    










