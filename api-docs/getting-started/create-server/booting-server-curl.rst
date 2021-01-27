.. _booting-server-with-curl:

Booting server (cURL)
---------------------

#. Issue the following cURL command.

   **Boot a server with cURL request**

   .. code::

       $ curl -s https://$API_ENDPOINT/v2/$TENANT_ID/servers \
              -X POST \
              -H "Content-Type: application/json" \
              -H "X-Auth-Token: $AUTH_TOKEN" \
              -H "X-Auth-Project-Id: test-project" \
              -d '{"server": {"name": "Ubuntu 11.10 server",
                 "imageRef": "3afe97b2-26dc-49c5-a2cc-a2fc8d80c001", "flavorRef": "6",
                 "config-drive": "true"}}' \
          | python -m json.tool

   The command returns a list of server properties, including the
   administrative password, the server ID, and links, as shown in the following
   output.

   **Boot a server with cURL response**

   .. code::

       {
           "server": {
               "OS-DCF:diskConfig": "AUTO",
               "adminPass": "T8GTdH29GmzG",
               "id": "1a861bf7-2a5e-40a4-acb3-1fb058cf2a74",
               "links": [
                   {
                       "href": "https://dfw.servers.api.rackspacecloud.com/v2/010101/servers/1a861bf7-2a5e-40a4-acb3-1fb058cf2a74",
                       "rel": "self"
                   },
                   {
                       "href": "https://dfw.servers.api.rackspacecloud.com/010101/servers/1a861bf7-2a5e-40a4-acb3-1fb058cf2a74",
                       "rel": "bookmark"
                   }
               ]
           }
       }

#. Copy the server ID value from the ``id`` field in the output.

   Copy the administrative password value from the ``adminPass`` field. You use
   this value to log into your server.



**Next topic:** :ref:`Getting server details<getting-server-details>`
