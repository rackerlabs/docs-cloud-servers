.. _listing-flavors-with-curl:

Listing flavors (cURL)
----------------------

#. Issue the following cURL command.

   **List flavors with cURL request**

   .. code::

       $ curl -s https://$API_ENDPOINT/v2/$TENANT_ID/flavors \
              -H "X-Auth-Token: $AUTH_TOKEN" | python -m json.tool

   For each flavor, the command returns the flavor ID, links, and name.

   The following output shows just the information returned for an 15 GB
   Compute1 server. For brevity, other flavors in the array were removed. Your
   listing will return all available flavors.

   **List flavors with cURL response**

   .. code::

       {
          "flavors":
            [
               {
                   "id": "6",
                   "links": [
                       {
                           "href": "https://dfw.servers.api.rackspacecloud.com/v2/820712/flavors/6",
                           "rel": "self"
                       },
                       {
                           "href": "https://dfw.servers.api.rackspacecloud.com/820712/flavors/6",
                           "rel": "bookmark"
                       }
                   ],
                   "name": "8GB Standard Instance"
               }
            ]
       }

#. Copy the ID of the flavor you want to use from the ``id`` field in the
   output. The value from this field will be used for the ``flavorRef`` field
   when you create a server.

   In this example, use the flavor ID for the 8GB Standard Instance, which is
   ``6``.

**Next topic:**  :ref:`Booting server<booting-server>`

