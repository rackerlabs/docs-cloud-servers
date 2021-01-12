.. _listing-images-with-curl:

Listing images (cURL)
---------------------

#. Issue the following cURL command.

   **List images with cURL request**

   .. code::

       $ curl -s https://$API_ENDPOINT/v2/$TENANT_ID/images \
              -H "X-Auth-Token: $AUTH_TOKEN" | python -m json.tool

   For each image, the command returns the ID, links, metadata, and name. The
   following output shows the information returned for the Ubuntu 11.10 image.
   For brevity, other images in the array are not shown.

   **List images with cURL response**

   .. code::

       {
           "images": [
               {
                   "OS-DCF:diskConfig": "AUTO",
                   "created": "2012-02-28T19:38:57Z",
                   "id": "3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
                   "links": [
                       {
                           "href": "https://dfw.servers.api.rackspacecloud.com/v2/010101/images/3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
                           "rel": "self"
                       },
                       {
                           "href": "https://dfw.servers.api.rackspacecloud.com/010101/images/3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
                           "rel": "bookmark"
                       },
                       {
                           "href": "https://dfw.servers.api.rackspacecloud.com/010101/images/3afe97b2-26dc-49c5-a2cc-a2fc8d80c001",
                           "rel": "alternate",
                           "type": "application/vnd.openstack.image"
                       }
                   ],
                   "metadata": {
                       "arch": "x86-64",
                       "auto_disk_config": "True",
                       "com.rackspace__1__build_core": "1",
                       "com.rackspace__1__build_managed": "1",
                       "com.rackspace__1__build_rackconnect": "1",
                       "com.rackspace__1__options": "0",
                       "com.rackspace__1__visible_core": "1",
                       "com.rackspace__1__visible_managed": "1",
                       "com.rackspace__1__visible_rackconnect": "1",
                       "image_type": "base",
                       "org.openstack__1__architecture": "x64",
                       "org.openstack__1__os_distro": "org.ubuntu",
                       "org.openstack__1__os_version": "11.10",
                       "os_distro": "ubuntu",
                       "os_type": "linux",
                       "os_version": "11.10",
                       "rax_managed": "false",
                       "rax_options": "0"
                   },
                   "minDisk": 10,
                   "minRam": 256,
                   "name": "Ubuntu 11.10 (Oneiric Oncelot)",
                   "progress": 100,
                   "status": "ACTIVE",
                   "updated": "2012-02-28T19:39:05Z"
               }
           ]
       }

#. Copy the image ID for the Ubuntu 11.10 image from the ``id`` field in the
   output.

   In this example, the ``id`` value for the Ubuntu 11.10 image is
   ``3afe97b2-26dc-49c50a2cc-a2fc8d80c001``.

**Next topic:** :ref:`Listing flavors<listing-flavors>`

