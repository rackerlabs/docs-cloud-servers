.. _booting-server-net-with-curl:

Booting server with network (cURL)
----------------------------------

Issue the following cURL command.

**Boot a server with network with cURL request**

.. code::

   $ curl https://$API_ENDPOINT/v2/$TENANT-ID/servers \
         -X POST \
         -H "X-Auth-Project-Id: $account" \
         -H "Content-Type: application/json" \
         -H "Accept: application/json" \
         -H "X-Auth-Token: $AUTH_TOKEN" \
         -d '{"server": {"name": "my_server_with_network",
            "imageRef": "d42f821e-c2d1-4796-9f07-af5ed7912d0e",
            "flavorRef": "2", "max_count": 1, "min_count": 1,
            "networks": [{"uuid": "538a112a-34d1-47ff-bf1e-c40639e886e2"},
            {"uuid": "00000000-0000-0000-0000-000000000000"},
            {"uuid": "11111111-1111-1111-1111-111111111111"}]}}' \
      | python -m json.tool

In addition to the isolated network, PublicNet and ServiceNet are attached to
the server. You must explicitly specify these networks to attach them to your
server.

The operation returns information about the new server, as shown in the
following output.

**Boot a server with network cURL response**

.. code::

   {
      "server":{
         "OS-DCF:diskConfig":"AUTO",
         "id":"2f881cd9-44c5-4178-a176-1bc07eb1cfb9",
         "links":[
            {
               "href":"https://dfw.servers.api.rackspacecloud.com/010101/servers/ed5c7754-29b6-45fa-96cb-ab64958c8c0a",
               "rel":"self"
            },
            {
               "href":"https://dfw.servers.api.rackspacecloud.com/010101/servers/ed5c7754-29b6-45fa-96cb-ab64958c8c0a",
               "rel":"bookmark"
            }
         ],
         "adminPass":"PkJ68cNqoQP2"
      }
   }




**Next topic:** :ref:`Getting network details<getting-network-details>`
