.. _boot-from-volume-extension:

================
Boot from volume
================

You can boot General Purpose and IO server instances from a volume instead of
an image, using the API operation, or nova ``boot`` command, with the
``block-device`` parameter of the server boot API operation. This moves the
system disk from local to remote, providing an a la carte storage experience
and separating the system disk from the server.

Boot from volume (BFV) functionality provides the following advantages: BFV
enables the diskless flavors (which can't work without BFV). BFV also allows
you to have a larger system disk for certain flavors, like windows flavors,
because the system disk no longer has to reside on the server itself.

.. note::
   General Purpose and IO servers may be booted from volume.

   Compute and Memory servers must be booted from volume, because image-based
   builds are not supported for these two flavor classes.

   Standard and OnMetal servers may not be booted from volume.

The :rax-devdocs:`Cloud Block Storage volumes API reference
<cloud-block-storage/v1/api-reference/cbs-volumes-operations/>`
provides useful operations for listing and working with volumes.


Create volume from image and boot instance
------------------------------------------

You can create a volume from an existing image, volume, or snapshot. This
procedure shows you how to create a bootable volume from an image, and use the
volume to boot an instance, instead of using an image.

Procedure: To create a bootable image and boot a server
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#. Create a bootable volume from an image.

   .. code::

      $ nova volume-create 100 --volume-type=SSD --display-name=BFB-test-SSD \
      --image-id=ff228647-fd57-47fe-b42d-2b7813bb9115

   Once the volume is online, the new volume's UUID will be passed to nova.

   Here is the JSON request body for the same request, if you don't use the
   nova client:

   .. code::

      {
         "volume": {
            "display_name": "BFB-test-SSD",
            "imageRef": "ff228647-fd57-47fe-b42d-2b7813bb9115",
            "availability_zone": null,
            "volume_type": "SSD",
            "display_description": null,
            "snapshot_id": null,
            "size": 100
         }
      }

#. Boot a server from the bootable volume:

   .. code::

      $ nova boot --flavor compute1-15 --block-device-mapping \
      vda=8dcf68f9-0321-42f3-a3dc-b861b9335a9b:::0 BFVServer

   .. note::
      Block device mapping is in the following format:
      <dev_name>=<id>:<type>:<size(GB)>:<delete_on_terminate>. Type and size
      can be left blank, delete on terminate can be expressed as ``True`` or
      ``1`` and ``False`` or ``0``.

   This command creates a Compute1 15GB server named BVFServer, which persists
   on server termination.

   Here is the JSON request body for the same request, if you don't use the
   nova client:

   .. code::

      {
         "server": {
            "name": "BFVServer",
            "imageRef": "",
            "block_device_mapping": [
               {
                  "volume_id": "8dcf68f9-0321-42f3-a3dc-b861b9335a9b",
                  "delete_on_termination": "0",
                  "device_name": "vda"
               }
            ],
            "flavorRef": "compute1-15",
            "max_count": 1,
            "min_count": 1,
            "networks": [
               {
                  "uuid": "00000000-0000-0000-0000-000000000000"
               },
               {
                  "uuid": "11111111-1111-1111-1111-111111111111"
               }
            ]
         }
      }

You can also create a bootable volume and boot a server in a single step.

Procedure: To create a bootable image and boot a server in a single step
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Boot server from bootable volume, without first creating the volume:

.. code::

   $ nova boot --flavor compute1-15 --block-device \
   source=image,id=e0b7734d-2331-42a3-b19e-067adc0da17d,dest=volume,size=100,shutdown=preserve,bootindex=0 BFVServer

This command creates a Compute1 15GB server from a volume that is prepped with
the image set by the id.

Use pre-made bootable volume to boot instance
---------------------------------------------

You can use a pre-made bootable volume use it to boot an instance, instead of
using an image. Pre-made bootable volumes are just Cloud Block Storage volumes
that include the "imageRef" key in the JSON object. The key needs to have the
value of an image's UUID in order to be bootable. If it is not bootable, it
will show an empty string.

The following example shows the nova command for booting a server from an
existing volume and creates a Compute1 15GB server named BVFServer:

.. code::

   $ nova boot --flavor compute1-15 --block-device-mapping vda=8dcf68f9-0321-42f3-a3dc-b861b9335a9b:::0 BFVServer

.. note::
   Block device mapping is in the following format:
   ``vda=<dev_id>:<type>:<size(GB)>:<delete_on_terminate>``.
   Type and size can be left blank, delete on terminate can be expressed as
   ``True`` (or ``1``) and ``False`` (or ``0``).

The following example shows a cURL command for booting a server from an
existing volume and creates a General Purpose v1 1GB server named BVFServer5:

.. code::

   $ curl -i 'https://preprod.ord.servers.api.rackspacecloud.com/v2/5892688/os-volumes_boot' \
   -X POST -H "Content-Type: application/json" -H "X-Auth-Token: $token" \
   -d '{"server":{"name":"BFVServer5","imageRef":"", \
   "block_device_mapping_v2":[{"boot_index":"0","uuid":"bb02b1a3-bc77-4d17-ab5b-421d89850fca","volume_size":"100", \
            "source_type":"image","destination_type":"volume","delete_on_termination":false}], \
      "flavorRef":"general1-1","max_count":1,"min_count":1, \
      "networks":[{"uuid":"00000000-0000-0000-0000-000000000000"},{"uuid":"11111111-1111-1111-1111-111111111111"}]}}' \
      | python -m json.tool


Here is the JSON request body for the same request, if you don't use the nova
client:

.. code::

   {
      "server": {
         "name": "BFVServer5",
         "imageRef": "",
         "block_device_mapping": [
            {
               "boot_index":"0"
               "uuid":"bb02b1a3-bc77-4d17-ab5b-421d89850fca",
               "volume_size":"100",
               "source_type":"image",
               "destination_type":"volume",
               "delete_on_termination":false
            }
         ],
         "flavorRef": "general1-1",
         "max_count": 1,
         "min_count": 1,
         "networks": [
            {
               "uuid": "00000000-0000-0000-0000-000000000000"
            },
            {
               "uuid": "11111111-1111-1111-1111-111111111111"
            }
         ]
      }
   }

API operations for creating or using bootable volumes
-----------------------------------------------------

The ``POST /servers`` operation creates a bootable volume and boots a server in
one step when you send the correct request body.

For an example of this operation, see
:ref:`Boot from volume operation <post-create-bootable-volume-and-server-servers>`.

Block-device-mapping attribute versus block-device attribute
------------------------------------------------------------

How do you know when to use the ``block_device_mapping`` (or
``--block-device-mapping``, in nova) attribute rather than the
``block_device_mapping_v2`` (or ``--block-device``, in nova) attribute?

Use ``block-device-mapping`` attribute, if you already have a bootable volume
or plan to create one in a separate step, prior to attempting the boot from
volume.

The ``block_device_mapping_v2`` attribute allows for more flexibility allowing
for various source types (image, volume, snapshot, or blank) and destination
types (local or volume). This attribute also supports more hypervisors and
doesn't require a volume to be set up first.

