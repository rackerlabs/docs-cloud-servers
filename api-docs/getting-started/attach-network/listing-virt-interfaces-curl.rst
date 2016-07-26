.. _listing-virt-interfaces-with-curl:

Listing virtual interfaces (cURL)
---------------------------------

Issue the following cURL command.

**List virtual interfaces with cURL request**

.. code::

   $ curl https://$API_ENDPOINT/v2/$TENANT-ID/servers/<instance_id>/os-virtual-interfacesv2  \
         -X GET -H "X-Auth-Token: $AUTH_TOKEN" | python -m json.tool

**Positional argument:**

-  ``instance_id``. The ID of the server instance for which you want to list
   virtual interfaces.

The operation returns a response as shown in the following example.

**List virtual interfaces with cURL response**

.. code::

   {
      "virtual_interfaces": [
         {
            "id": "a589b11b-cd51-4274-8ec0-832ce799d156",
            "ip_addresses": [
               {
                  "address": "2001:4800:7810:0512:d87b:9cbc:ff04:850c",
                  "network_id": "ba122b32-dbcc-4c21-836e-b701996baeb3",
                  "network_label": "public"
               },
               {
                  "address": "64.49.226.149",
                  "network_id": "ba122b32-dbcc-4c21-836e-b701996baeb3",
                  "network_label": "public"
               }
            ],
            "mac_address": "BC:76:4E:04:85:0C"
         },
         {
            "id": "de7c6d53-b895-4b4a-963c-517ccb0f0775",
            "ip_addresses": [
               {
                  "address": "192.168.0.2",
                  "network_id": "f212726e-6321-4210-9bae-a13f5a33f83f",
                  "network_label": "superprivate_xml"
               }
            ],
            "mac_address": "BC:76:4E:04:85:20"
         },
         {
            "id": "e14e789d-3b98-44a6-9c2d-c23eb1d1465c",
            "ip_addresses": [
               {
                  "address": "10.181.1.30",
                  "network_id": "3b324a1b-31b8-4db5-9fe5-4a2067f60297",
                  "network_label": "private"
               }
            ],
            "mac_address": "BC:76:4E:04:81:55"
         }
      ]
   }

**Next topic:**  :ref:`Deleting a virtual interface<deleting-virt-interface>`