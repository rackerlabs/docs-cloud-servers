.. _post-create-volume-os-volumes:

Create volume
-------------

.. code::

    POST /os-volumes

This operation creates a new data volume.

This table shows the possible response codes for this operation:


+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200 203                  |Success                  |Request succeeded.       |
+-------------------------+-------------------------+-------------------------+
|400                      |Error                    |A general error has      |
|                         |                         |occured.                 |
+-------------------------+-------------------------+-------------------------+
|401                      |Unauthorized             |Unauthorized.            |
+-------------------------+-------------------------+-------------------------+
|403                      |Forbidden                |Forbidden.               |
+-------------------------+-------------------------+-------------------------+
|405                      |Bad Method               |Bad method.              |
+-------------------------+-------------------------+-------------------------+
|409                      |Conflicting Reqest       |Conflicting request.     |
+-------------------------+-------------------------+-------------------------+
|413                      |Over Limit               |The number of items      |
|                         |                         |returned is above the    |
|                         |                         |allowed limit.           |
+-------------------------+-------------------------+-------------------------+
|500                      |API Fault                |API fault.               |
+-------------------------+-------------------------+-------------------------+
|503                      |Service Unavailable      |The requested service is |
|                         |                         |unavailable.             |
+-------------------------+-------------------------+-------------------------+

Request
^^^^^^^

This table shows the body parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**volume**                |Object                  |A container for volume   |
|                          |                        |creation response.       |
+--------------------------+------------------------+-------------------------+
|volume.\ **display_name** |String *(Optional)*     |The name assigned to the |
|                          |                        |volume.                  |
+--------------------------+------------------------+-------------------------+
|volume.\                  |String *(Optional)*     |The description for the  |
|**display_description**   |                        |volume.                  |
+--------------------------+------------------------+-------------------------+
|volume.\ **volume_type**  |String                  |The type of volume,      |
|                          |                        |either ``SATA`` or       |
|                          |                        |``SSD``. Alternaltely,   |
|                          |                        |you can use the UUID     |
|                          |                        |volume id for the volume |
|                          |                        |instead of the name. The |
|                          |                        |default is ``SATA``.     |
+--------------------------+------------------------+-------------------------+
|volume.\ **size**         |Integer                 |The size of the volume   |
|                          |                        |in gibibytes (GiB). The  |
|                          |                        |valid range for ``SATA`` |
|                          |                        |is 75-1024. The valid    |
|                          |                        |range for ``SSD`` is 50- |
|                          |                        |1024.                    |
+--------------------------+------------------------+-------------------------+

**Example Create volume: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "volume": {
           "display_name": "vol-001",
           "display_description": "Another volume.",
           "size": 100,
           "volume_type": "SATA"
       }
   }

Response
^^^^^^^^

This table shows the body parameters for the response:

+------------------------------------+-------------------+--------------------+
|Name                                |Type               |Description         |
+====================================+===================+====================+
|**volume**                          |Object             |A container for     |
|                                    |                   |volume creation     |
|                                    |                   |response.           |
+------------------------------------+-------------------+--------------------+
|volume.\ **status**                 |String             |The state of the    |
|                                    |                   |volume. This will   |
|                                    |                   |be ``available``    |
|                                    |                   |when volume is      |
|                                    |                   |created and ready   |
|                                    |                   |for use.            |
+------------------------------------+-------------------+--------------------+
|volume.\ **display_name**           |String             |The name assigned   |
|                                    |                   |to the volume.      |
+------------------------------------+-------------------+--------------------+
|volume.\ **attachments**            |Array              |An array of volume  |
|                                    |                   |attachments.        |
+------------------------------------+-------------------+--------------------+
|volume.availability_zone            |String             |This parameter is   |
|                                    |                   |no longer used and  |
|                                    |                   |is always set to    |
|                                    |                   |``nova``.           |
+------------------------------------+-------------------+--------------------+
|volume.\ **created_at**             |Date               |The date and time   |
|                                    |                   |of volume creation. |
+------------------------------------+-------------------+--------------------+
|volume.\ **display_description**    |String             |The description for |
|                                    |                   |the volume.         |
+------------------------------------+-------------------+--------------------+
|volume.\ **image_id**               |String             |The image_id use    |
|                                    |                   |for the volume. If  |
|                                    |                   |no image was        |
|                                    |                   |specified, this     |
|                                    |                   |will be ``null``.   |
+------------------------------------+-------------------+--------------------+
|volume.\ **volume_type**            |String             |The type of volume, |
|                                    |                   |either ``SATA`` or  |
|                                    |                   |``SSD``.            |
|                                    |                   |Alternaltely, you   |
|                                    |                   |can use the UUID    |
|                                    |                   |volume id for the   |
|                                    |                   |volume instead of   |
|                                    |                   |the name. The       |
|                                    |                   |default is ``SATA``.|
+------------------------------------+-------------------+--------------------+
|volume.\ **snapshot_id**            |Uuid               |The snapshot from   |
|                                    |                   |which to create a   |
|                                    |                   |volume, if any.     |
+------------------------------------+-------------------+--------------------+
|volume.\ **metadata**               |String             |Any metadata for    |
|                                    |                   |the volume.         |
+------------------------------------+-------------------+--------------------+
|volume.\ **id**                     |String             |The volume id.      |
+------------------------------------+-------------------+--------------------+
|volume.\ **size**                   |Integer            |The size of the     |
|                                    |                   |volume in gibibytes |
|                                    |                   |(GiB). The valid    |
|                                    |                   |range for ``SATA``  |
|                                    |                   |is 75-1024. The     |
|                                    |                   |valid range for     |
|                                    |                   |``SSD`` is 50-1024. |
+------------------------------------+-------------------+--------------------+

**Example Create volume: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 310
       Content-Type: application/json
       Date: Thu, 16 Jul 2015 16:10:58 GMT, Thu, 16 Jul 2015 16:10:59 GMT
       Location: http://dfw.servers.api.rackspacecloud.com/v2/123456/os-volumes/6c101c70-343f-2971-89fd-c334f1825df4
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-44633234-9922-4490-9d55-683919790289


.. code::

   {
     "volume": {
       "status": "creating",
       "display_name": "vol-001",
       "attachments": [],
       "availability_zone": "nova",
       "bootable": "false",
       "encrypted": false,
       "created_at": "2015-06-10T16:14:13.414451",
       "display_description": "Another volume.",
       "volume_type": "SATA",
       "snapshot_id": null,
       "source_volid": null,
       "metadata": {},
       "id": "f7b5e147-ac9a-4fca-bbd4-7d6363739b0e",
       "size": 100
     }
   }




