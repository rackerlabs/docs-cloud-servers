.. _listing-networks-with-curl:

Listing networks (cURL)
-----------------------

Issue the following cURL command.

**List networks with cURL request**

.. code::

   $ curl https://$API_ENDPOINT/v2/$TENANT-ID/os-networksv2 \
         -X GET -H "X-Auth-Token: $AUTH_TOKEN" | python -m json.tool

For each isolated network, the operation returns the CIDR. Additionally, for
isolated networks and Rackspace networks, the operation returns the network ID
and label.

**List networks with cURL response**

.. code::

   {
      "networks":[
         {
            "cidr":"192.168.0.0/24",
            "id":"1f84c238-b05a-4374-a0cb-aa6140032cd1",
            "label":"new_network"
         },
         {
            "id":"00000000-0000-0000-0000-000000000000",
            "label":"public"
         },
         {
            "id":"11111111-1111-1111-1111-111111111111",
            "label":"private"
         }
      ]
   }

**Next topic:**  :ref:`Booting server<booting-server-with-net>`