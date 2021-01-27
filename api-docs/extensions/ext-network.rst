.. _networks-extension:

=================
Network extension
=================

Cloud Networks lets you create a virtual Layer 2 network, known as an
isolated network, which gives you greater control and security when you
deploy web applications.

When you create a Cloud Server, Cloud Networks enables you to attach one or more networks 
to your server. You can attach an isolated network that you have created or a Rackspace 
network.

If you install the Cloud Networks virtual interface extension, you can
create a virtual interface to a specified Rackspace or isolated network
and attach that network to an existing server instance. You can also
list virtual interfaces for and delete virtual interfaces from a server
instance.

Cloud Networks enables you to attach one or more of the following
networks to your server:

*  **PublicNet**. Provides access to the Internet, Rackspace services
   such as Cloud Monitoring, Managed Operations Service Level Support,
   RackConnect, Cloud Backup, and certain operating system updates.

   When you list networks through Cloud Networks, PublicNet is labeled
   ``public``.

*  **ServiceNet**. Provides access to Rackspace services such as Cloud
   Files, Cloud Databases, and Cloud Backup, and to certain packages and
   patches through an internal only, multi-tenant network connection
   within each Rackspace data center.

   When you list networks through Cloud Networks, ServiceNet is labeled
   ``private``.

   You can use ServiceNet for communications among web servers,
   application servers, and database servers without incurring bandwidth
   charges. However, without an isolated network, you must apply
   security rules to protect data integrity. When you add or remove a
   server, you must update the security rules on individual servers to
   permit or deny connections from newly added servers or removed
   servers.

*  **Isolated**. Enables you to deploy web applications on a virtual
   Layer 2 network that you create through Cloud Networks. Keeps your
   server separate from PublicNet, ServiceNet, or both. When you create
   a isolated network, it is associated with your tenant ID.


.. note::

   If you want to delete an isolated network, the network cannot be
   attached to any server. If there is a virtual interface for the isolated
   network, delete that first and then you can delete the network.

API operations for networks extension
-------------------------------------

For examples of these operations, see the following operations:

- :ref:`List networks <get-retrieve-list-of-networks-os-networksv2>`
- :ref:`Create network <post-create-network-os-networksv2>`
- :ref:`Create server with network <post-create-server-with-network-servers>`
- :ref:`Show network details <get-show-network-os-networksv2-id>`
- :ref:`Delete network <delete-delete-network-os-networksv2-id>`

