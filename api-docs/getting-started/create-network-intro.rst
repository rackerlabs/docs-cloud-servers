.. _create-network-intro:

=========================
Create your first network
=========================

Rackspace first introduced networking services that were based on the OpenStack
Nova-Network API and exposed these services via the ``/os-networksv2`` Cloud
Servers extension.

These examples walk you through the steps to create an isolated network and
create a server that is attached your isolated network. The simple exercises
show you how to access the Networks extension API through nova client commands
or cURL commands so that you can quickly create isolated networks and servers.

The exercises also help you learn how cURL commands and the Networks extension
API work.

.. Note::

   This version of the network service is now superseded by the current
   networking API, based on OpenStack Neutron, which offers a richer suite of
   networking services. To learn more about neutron network operations, see
   :rax-devdocs:`Cloud Networks API reference <cloud-networks/v2/api-reference/#api-reference>`.

.. toctree::
   :maxdepth: 2

   Creating network <create-network/creating-network>
   Listing flavors <create-network/listing-networks>
   Booting a new server with your cloud network <create-network/booting-server-with-net>
   Getting network details <create-network/getting-network-details>
   Deleting your cloud network <create-network/deleting-network>