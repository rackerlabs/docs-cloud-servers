.. _creating-network-with-curl:

Creating network (cURL)
-----------------------

#. Issue the following cURL command.

   **Create network with cURL request**

   .. code::

       $ curl -s https://$API_ENDPOINT/v2/$TENANT-ID/os-networksv2 \
              -X POST \
              -H "X-Auth-Project-Id: $account" \
              -H "Content-Type: application/json" \
              -H "Accept: application/json" \
              -H "X-Auth-Token: $AUTH_TOKEN" \
              -d '{"network": {"cidr": "192.168.0.0/24", "label": "superprivate"}}' | python -m json.tool



   The operation returns the CIDR, ID, and label for the isolated network, as
   shown in the following JSON response.

   **Create network with cURL response**

   .. code::

       {
           "network": {
               "cidr": "192.168.0.0/24",
               "id": "1ff4489e-db0e-45a6-8c9f-4616c6ef5db1",
               "label": "superprivate"
           }
       }


#. Copy the ``id`` value from the output. In this example, the ``id`` value is
   ``1f84c238-b05a-4374-a0cb-aa6140032cd1``, but use the value returned for
   your network.


**Next topic:**  :ref:`Listing networks<listing-networks>`

