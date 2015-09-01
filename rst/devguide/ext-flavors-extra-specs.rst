=============================
Flavors Extra Specs Extension
=============================

The flavors extra spec extension adds the ``OS-FLV-WITH-EXT-SPECS:extra_specs`` attribute
on flavors, providing additional information about the flavor such as identifying the flavor class.

Changes to Get flavor details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A **GET** request on the **/flavors/{id}** resource returns the ``OS-FLV-WITH-EXT-SPECS:extra_specs`` 
extended attribute.

**Example: Response: JSON**

.. code::

   {
     "flavor":{
       "OS-FLV-WITH-EXT-SPECS:extra_specs":{
         "resize_policy_class":"performance_flavor",
         "policy_class":"performance_flavor",
         "class":"performance1",
         "disk_io_index":"40",
         "number_of_data_disks":"1"
       },
       "name":"8 GB Performance",
       "links":[
         {
            "href":"https://ord.servers.api.rackspacecloud.com/v2/525722/flavors/performance1-8",
            "rel":"self"
         },
         {
            "href":"https://ord.servers.api.rackspacecloud.com/525722/flavors/performance1-8",
            "rel":"bookmark"
         }
       ],
       "ram":8192,
       "vcpus":8,
       "swap":"",
       "rxtx_factor":1600.0,
       "OS-FLV-EXT-DATA:ephemeral":80,
       "disk":40,
       "id":"performance1-8"
     }
   }