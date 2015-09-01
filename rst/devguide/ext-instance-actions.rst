==========================
Server Actions Extension
==========================

The server actions extension allows you to view a log of events and actions
taken on a server. First do a GET $endpoint/servers/{server-id}/os-instance-actions
to see a list of the actions, then you can show more details with GET
$endpoint/servers/{server-id}/os-instance-actions/{request-id}.

List server actions and show action details operations
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Click the following link to see examples of these operations.

.. toctree::
    :maxdepth: 2

	Retrieve list of server actions <api-operations/extensions/get-retrieve-list-of-server-actions-servers-server-id-os-instance-actions>
	Show details of specified server action <api-operations/extensions/get-retrieve-log-details-for-a-specified-server-action-servers-server-id-os-instance-actions-request-id>
	

