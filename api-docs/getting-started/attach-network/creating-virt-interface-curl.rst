.. _creating-virt-interface-with-curl:

Creating a virtual interface (cURL)
-----------------------------------

Issue the following cURL command.

**Create a virtual interface with cURL request**

.. code::

   $ curl https://$API_ENDPOINT/v2/$TENANT-ID/servers/<instance_id>/os-virtual-interfacesv2 \
         -X POST \
         -H "Content-Type: application/json" \
         -H "Accept: application/json" \
         -H "X-Auth-Token: $AUTH_TOKEN" \
         -d '{"virtual_interface": {"network_id": "<network_id>"}}'| python -m json.tool

**Positional arguments:**

-  ``instance_id``. The ID of the server instance to which you want to connect
   the virtual interface.

-  ``network_id``. The ID of the network for which you want to create a virtual
   interface.

The operation returns a response as shown in the following example.

**Create a virtual interface with cURL response**

.. code::

   {
      "virtual_interfaces":[
         {
            "mac_address":"FE:ED:FA:00:08:93",
            "id":"045f195f-3347-487b-8e80-8ee3390eda56",
            "ip_addresses":[
               {
                  "address":"192.168.0.1",
                  "network_id":"196a0246-86cc-46fa-9ecf-850f67c2cb7c",
                  "network_label":"added_network"
               }
            ]
         }
      ]
   }

**Next topic:**  :ref:`Listing virtual interfaces for a server<listing-virt-interfaces>`
