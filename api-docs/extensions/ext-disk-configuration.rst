.. _disk-configuration-extension:

============================
Disk Configuration Extension
============================

The disk configuration extension adds the ``OS-DCF:diskConfig`` attribute to
servers, which controls how the disk is partitioned when servers are created,
rebuilt, or resized. A server gets the ``OS-DCF:diskConfig`` value from the
image with which it was created, based on the image's ``auto-disk-config``
attribute. To override the inherited setting, you can include the
``OS-DCF:diskConfig`` attribute in the request body of a server create,
rebuild, or resize request.

.. important::
   If an image has ``auto-disk-config`` value of ``MANUAL``or ``DISABLED``, you
   cannot create a server from that image with a ``OS-DCF:diskConfig`` value of
   ``AUTO``.

Valid ``OS-DCF:diskConfig`` values are:

*  ``AUTO``. The server is built with a single partition the size of the target
   flavor disk. The file system is automatically adjusted to fit the entire
   partition. This keeps things simple and automated. ``AUTO`` is valid only
   for images and servers with a single partition that use the EXT3 file
   system. This is the default setting for applicable Rackspace base images.
*  ``MANUAL``. The server is built using whatever partition scheme and file
   system is in the source image. If the target flavor disk is larger, the
   remaining disk space is left unpartitioned. This enables images to have
   non-EXT3 file systems, multiple partitions, and so on, and enables you to
   manage the disk configuration.

.. note::
   Although Rackspace Windows images are configured with a ``auto-disk-config``
   value of ``MANUAL``, the NTFS file system expands to the entire partition on
   only the first boot.

Resizing down requires the server to have a ``OS-DCF:diskConfig`` value of
``AUTO``.

The namespace for this extended attribute is:

.. code::

    xmlns:OS-DCF="http://docs.openstack.org/compute/ext/disk_config/api/v1.1"

Changes to Get Server/Image Details
-----------------------------------

A ``GET`` request on the ``/servers/detail``, ``/servers/{id}``,
``/images/detail``, or ``/images/{id}`` resource returns the
``OS-DCF:diskConfig`` extended attribute. See the following operations:

- :ref:`List Servers <get-retrieves-a-list-of-servers-servers>`

- :ref:`Show Server Details <get-retrieve-server-details-servers-server-id>`

- :ref:`List Images <api-operations-images>`

- :ref:`Show Image Details <get-retrieve-image-details-images-image-id>`

Changes to Rebuild Server
-------------------------

You can set the ``OS-DCF:diskConfig`` attribute when you rebuild a server. In
the following examples, the ``OS-DCF:diskConfig`` attribute is set to
``MANUAL``, which allows unused disk space to be used for other partitions
after the server is rebuilt.

If you do not set the ``OS-DCF:diskConfig`` attribute is not set during the
rebuild, the original value of the attribute is retained.

**Example: Rebuild Server with OS-DCF:diskConfig: JSON Request**

.. code::

                        {
    "rebuild" : {
             "name" : "new-server-test",
             "imageRef" : "d42f821e-c2d1-4796-9f07-af5ed7912d0e",
             "flavorRef" : "2",
             "OS-DCF:diskConfig" : "manual",
             "adminPass" : "diane123",
             "metadata" : {
                  "My Server Name" : "Apache1"
                   },
             "personality" : [
                 {
                   "path" : "/etc/banner.txt",
                   "contents" : "ICAgICAgDQoiQSBjbG91ZCBkb2VzIG5vdCBrbm93IHdoeSBp dCBtb3ZlcyBpbiBqdXN0IHN1Y2ggYSBkaXJlY3Rpb24gYW5k IGF0IHN1Y2ggYSBzcGVlZC4uLkl0IGZlZWxzIGFuIGltcHVs c2lvbi4uLnRoaXMgaXMgdGhlIHBsYWNlIHRvIGdvIG5vdy4g QnV0IHRoZSBza3kga25vd3MgdGhlIHJlYXNvbnMgYW5kIHRo ZSBwYXR0ZXJucyBiZWhpbmQgYWxsIGNsb3VkcywgYW5kIHlv dSB3aWxsIGtub3csIHRvbywgd2hlbiB5b3UgbGlmdCB5b3Vy c2VsZiBoaWdoIGVub3VnaCB0byBzZWUgYmV5b25kIGhvcml6 b25zLiINCg0KLVJpY2hhcmQgQmFjaA=="
                 }
               ]
        }
    }

Changes to Resize Server
------------------------

You can set the ``OS-DCF:diskConfig`` attribute when you resize a server, which
enables you to change the value of the attribute when you scale a server up or
down.

If you do not set the ``OS-DCF:diskConfig`` attribute during the resize, the
original value of the attribute is retained.

**Example: Resize Server with OS-DCF:diskConfig: JSON Request**

.. code::

                        {
        "resize" : {
            "flavorRef" : "3",
            "OS-DCF:diskConfig" : "manual"
        }
    }

Changes to Create Server
------------------------

When you create a server from an image with the ``auto-disk-config`` value set
to ``TRUE``, the server is built with a single partition that is expanded to
the disk size of the flavor selected. If the image has the ``auto-disk-config``
value set to ``FALSE`` or ``DISABLED``, the server is built by using the
partition scheme and file system that is in the source image. If the target
flavor disk is larger, remaining disk space is left unpartitioned. A server
gets the ``OS-DCF:diskConfig`` attribute value from the image from which it is
created, based on the image's ``auto-disk-config`` attribute.

For an example of this operation, see
:ref:`Create server with disk config operation <post-create-server-with-disk-config-servers>`.
