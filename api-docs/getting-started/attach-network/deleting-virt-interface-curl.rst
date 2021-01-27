.. _deleting-virt-interface-with-curl:

Deleting a virtual interface (cURL)
-----------------------------------

Issue the following command to detach the virtual interface from the server.

**Delete a virtual interface with cURL request**

.. code::

   $ curl -i https://$API_ENDPOINT/v2/$TENANT_ID/servers/<instance_id>/os-virtual-interfacesv2/<interface_id> \
         -X DELETE -H "X-Auth-Token: $AUTH_TOKEN"

**Positional arguments:**

-  ``instance_id``. The ID of the server instance from which you want to detach
   the virtual interface.

-  ``interface_id``. The ID of the virtual interface that you want to delete.

If the delete operation was successful, the HTTP header shows the 204 status
code, as shown in the following output.

**Delete a virtual interface with cURL request**

.. code::

   HTTP/1.1 204 No Content
   Date: Thu, 16 Aug 2012 17:19:53 GMT
   Content-Length: 0
   Content-Type: application/json
   X-Compute-Request-Id: req-3bdafeb2-d4b1-41c3-ab19-d310f3f270d3
   Server: Jetty(8.0.y.z-SNAPSHOT)

