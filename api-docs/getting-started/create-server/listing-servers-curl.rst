.. _listing-servers-with-curl:

Listing servers (cURL)
----------------------

#. Issue the following command.

   **List servers with cURL request**

   .. code::

       $ curl -s https://$API_ENDPOINT/v2/$TENANT_ID/servers/detail \
              -H "X-Auth-Token: $AUTH_TOKEN" | python -m json.tool

   For each server, the command returns the disk configuration, the addresses
   of any attached networks, flavor and image information, the server ID, and
   the server status. The networks include any isolated networks that you have
   created and Rackspace public and private networks.

   The following output shows the list servers information, including
   information for the server that you just created.

   **List servers with cURL response**

   .. code::

       {
           "servers": [
               {
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
                   "progress": 75,
                   "status": "BUILD",
                   "tenant_id": "010101",
                   "updated": "2012-08-16T17:14:50Z",
                   "user_id": "170454"
               },
               {
                   "OS-DCF:diskConfig": "AUTO",
                   "OS-EXT-STS:power_state": 1,
                   "OS-EXT-STS:task_state": null,
                   "OS-EXT-STS:vm_state": "active",
                   "accessIPv4": "",
                   "accessIPv6": "",
                   "addresses": {
                       "private": [
                           {
                               "addr": "10.180.13.75",
                               "version": 4
                           }
                       ],
                       "public": [
                           {
                               "addr": "2001:4800:780e:0510:d87b:9cbc:ff04:3e81",
                               "version": 6
                           },
                           {
                               "addr": "50.56.186.185",
                               "version": 4
                           }
                       ]
                   },
                   "created": "2012-05-15T15:47:37Z",
                   "flavor": {
                       "id": "6",
                       "links": [
                           {
                               "href": "https://dfw.servers.api.rackspacecloud.com/010101/flavors/6",
                               "rel": "bookmark"
                           }
                       ]
                   },
                   "hostId": "1d65b563fc573c2eb544319e0af598f2b2c5f84f75de252db3757cd3",
                   "id": "a09e7493-7429-41e1-8d3f-384d7ece09c0",
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
                           "href": "https://dfw.servers.api.rackspacecloud.com/v2/010101/servers/a09e7493-7429-41e1-8d3f-384d7ece09c0",
                           "rel": "self"
                       },
                       {
                           "href": "https://dfw.servers.api.rackspacecloud.com/010101/servers/a09e7493-7429-41e1-8d3f-384d7ece09c0",
                           "rel": "bookmark"
                       }
                   ],
                   "metadata": {},
                   "name": "UbuntuDevStack",
                   "progress": 100,
                   "status": "ACTIVE",
                   "tenant_id": "010101",
                   "updated": "2012-05-15T15:55:00Z",
                   "user_id": "170454"
               }
           ]
       }

#. Look for the server you just created in the list of servers. Servers are
   listed by server ID.

**Next topic:** :ref:`Deleting server<deleting-server>`
