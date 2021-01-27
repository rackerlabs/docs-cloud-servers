.. _deleting-server-with-curl:

Deleting server (cURL)
----------------------

To delete your server with cURL, you need the server ID.

Issue the following command,specifying the ID for the server that you want to
delete.

**Delete a server with cURL request**

.. code::

   $ curl -i https://$API_ENDPOINT/v2/$TENANT_ID/servers/<id> \
          -X DELETE \
          -H "X-Auth-Token: $AUTH_TOKEN"

Where ``id`` is the ID of the server that you want to delete.


If the delete operation was successful, it returns a ``HTTP 204`` status code,
as shown in the following output.

**Delete a server with cURL response**

.. code::

   HTTP/1.1 204 No Content
   Date: Thu, 16 Aug 2012 17:19:53 GMT
   Content-Length: 0
   Content-Type: application/json
   X-Compute-Request-Id: req-3bdafeb2-d4b1-41c3-ab19-d310f3f270d3
   Server: Jetty(8.0.y.z-SNAPSHOT)

**Next topic:** :ref:`Create your first network<create-network-intro>`

