.. _os_instance-actions-extension:

OS Instance Actions Extension
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The server actions extension allows you to view a log of events and actions
taken on a server. First do a ``GET $endpoint/servers/{server-id}/os-instance-actions``
to see a list of the actions, then you can show more details with ``GET
$endpoint/servers/{server-id}/os-instance-actions/{request-id}``.

List server actions and show action details operations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For examples of these operations, see the following operations:

- :ref:`List OS instance actions<list-instance-actions>`
- :ref:`Show details for a OS instance action<get-instance-action-details>`


