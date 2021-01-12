.. _getting-server-details-with-curl:

Getting server details (cURL)
-----------------------------

#. Issue the following command.

   **Get server details with cURL request**

   .. code::

      $ curl -s https://$API_ENDPOINT/v2/$TENANT_ID/servers/<id> \
         -H "X-Auth-Token: $AUTH_TOKEN" | python -m json.tool

   Where ``id`` is the server ID that you copied in
   :ref:`Booting server (cURL)<booting-server-with-curl>`.

   The command shows information for your server, including its private and
   public IP addresses, and status, as shown in the following output.

   **Get server details with cURL response**

   .. code::

      {
       "server": {
         "OS-DCF:diskConfig": "AUTO",
         "OS-EXT-STS:power_state": 0,
         "OS-EXT-STS:task_state": "spawning",
         "OS-EXT-STS:vm_state": "building",
         "accessIPv4": "",
         "accessIPv6": "",
         "addresses": {
            "private": [
               {
                  "addr": "10.180.16.21",
                  "version": 4
               }
            ],
            "public": [
               {
                  "addr": "2001:4800:780e:0510:d87b:9cbc:ff04:4bac",
                  "version": 6
               },
               {
                  "addr": "198.101.242.47",
                  "version": 4
               }
            ]
         },
         "created": "2012-08-16T17:11:43Z",
         "flavor": {
            "id": "6",
            "links": [
               {
                  "href": "https://dfw.servers.api.rackspacecloud.com/010101/flavors/6",
                  "rel": "bookmark"
               }
            ]
         },
         "hostId": "692f611d2d84e5368b5995d7733ca5f175dc670eda91eded50a47eab",
         "id": "1a861bf7-2a5e-40a4-acb3-1fb058cf2a74",
         "image": {
            "id": "3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
            "links": [
               {
                  "href": "https://dfw.servers.api.rackspacecloud.com/010101/images/3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
                  "rel": "bookmark"
               }
            ]
         },
         "links": [
            {
               "href": "https://dfw.servers.api.rackspacecloud.com/v2/010101/servers/1a861bf7-2a5e-40a4-acb3-1fb058cf2a74",
               "rel": "self"
            },
            {
               "href": "https://dfw.servers.api.rackspacecloud.com/010101/servers/1a861bf7-2a5e-40a4-acb3-1fb058cf2a74",
               "rel": "bookmark"
            }
         ],
         "metadata": {
            "My Server Name": "Ubuntu 11.10 server"
         },
         "name": "myUbuntuServer",
         "progress": 50,
         "status": "BUILD",
         "tenant_id": "010101",
         "updated": "2012-08-16T17:12:46Z",
         "user_id": "170454"
       }
      }


#. Run the command until the status of your server is ``ACTIVE``. Typically,
   servers take a few minutes to build.

#. Copy the ``public`` IP version 4 address from the output. Use this address
   when you log into your server.

**Next topic:** :ref:`Listing servers<listing-servers>`

