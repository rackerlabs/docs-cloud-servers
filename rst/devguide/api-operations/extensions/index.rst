Extension operations
---------------------

This section describes the API operations that extend the server API.

.. toctree::
    :maxdepth: 2

    [SCHED IMAGES] Enable scheduled images for server <post-enable-scheduled-images-servers-server-id-rax-si-scheduled-image>
    [SCHED IMAGES] Show scheduled images for server <get-show-scheduled-images-servers-server-id-rax-si-scheduled-image>
    [SCHED IMAGES] Disable scheduled images for server <delete-disable-scheduled-images-servers-server-id-rax-si-scheduled-image>

	[DISK CONFIG] Create server with Disk Config <get-create-server-with-disk-config-servers>

	[KEY PAIRS] Create key pair <post-create-a-server-key-pair-os-keypairs>
	[KEY PAIRS] Import key pair <post-import-a-server-key-pair-os-keypairs>
	[KEY PAIRS] List key pairs <get-retrieve-list-of-key-pairs-os-keypairs>
	[KEY PAIRS] Delete key pair <delete-delete-key-pair-os-keypairs-keypair-name>

	[NETWORKS] List networks <get-retrieve-list-of-networks-os-networksv2>
	[NETWORKS] Create network <post-create-network-os-networksv2>
	[NETWORKS] Show network details <get-show-network-os-networksv2-id>
	[NETWORKS] Delete network <delete-delete-network-os-networksv2-id>

	[VIRT INT] List virtual interfaces <get-retrieve-list-of-virtual-interfaces-servers-server-id-os-virtual-interfacesv2>
	[VIRT INT] Create virtual interface <post-create-virtual-interface-and-attach-to-server-servers-server-id-os-virtual-interfacesv2>
	[VIRT INT] Delete virtual interface <delete-delete-virtual-interface-servers-server-id-os-virtual-interfacesv2-interface-id>

	[CONSOLE] Retrieve console output for server <post-get-console-servers-server-id-action>

	[VOLUMES] List volumes <get-retrieve-list-of-volumes-os-volumes>
	[VOLUMES] Create volume <post-create-volume-os-volumes>
	[VOLUMES] Show volume details <get-retrieve-volume-details-os-volumes-id>
	[VOLUMES] Delete volume <delete-delete-volume-os-volumes-id>

	[FLV EXTRA SPEC] Show extra specs for flavor <get-show-flavor-with-extra-specs-flavors-flavor-id>
	
	[FLV OS SPECS] List OS extra specs for flavor <get-list-extra-specs-for-flavors-flavors-flavor-id-os-extra-specs>
	[FLV OS SPECS] Show details for OS extra specs for flavor <get-get-details-for-specified-flavor-extra-spec-flavors-flavor-id-os-extra-specs-key-id>
	
	[QUOTAS] List quotas for a tenant <get-retrieve-quotas-os-quota-sets-tenant-id>
	
	[USED LIMITS] List limits including used <get-retrieve-list-of-limits-including-used-limits-limits>
