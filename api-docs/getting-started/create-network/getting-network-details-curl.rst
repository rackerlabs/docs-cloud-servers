.. _getting-network-details-with-curl:

Getting network details (cURL)
------------------------------

Issue the following cURL command.

**Get network details with cURL request**

.. code::

   $ curl https://$API_ENDPOINT/v2/$TENANT_ID/os-networksv2/<id> \
         -X GET \
         -H "X-Auth-Project-Id: $account" \
         -H "Accept: application/json" \
         -H "Content-Type: application/json"\
         -H "X-Auth-Token: $AUTH_TOKEN" | python -m json.tool

**Positional argument:**

-  ``id``. The ID of the network for which you want to show information.

The operation returns the CIDR, network ID, and label, as shown in the
following output.

**Get network details with cURL response**

.. code::

   {
      "network": {
         "cidr": "192.168.0.0/24",
         "id": "f212726e-6321-4210-9bae-a13f5a33f83f",
         "label": "superprivate_xml"
      }
   }

**Next topic:** :ref:`Deleting network<deleting-network>`

