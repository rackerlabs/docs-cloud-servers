
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

Retrieve list of volumes
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /os-volumes

Retrieve list of volumes for your account.

Retrieves the list of volumes for your account.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200 203                   |Success                  |Request succeeded.       |
+--------------------------+-------------------------+-------------------------+
|400                       |Error                    |A general error has      |
|                          |                         |occured.                 |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |Unauthorized.            |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Forbidden.               |
+--------------------------+-------------------------+-------------------------+
|405                       |Bad Method               |Bad method.              |
+--------------------------+-------------------------+-------------------------+
|409                       |Conflicting Reqest       |Conflicting request.     |
+--------------------------+-------------------------+-------------------------+
|413                       |Over Limit               |The number of items      |
|                          |                         |returned is above the    |
|                          |                         |allowed limit.           |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""






This operation does not accept a request body.




**Example Retrieve list of volumes: JSON request**


.. code::

    X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
    Content-Type: application/json
    Accept: application/json


Response
""""""""""""""""


This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|volumes                   |Object                   |An array of volumes.     |
+--------------------------+-------------------------+-------------------------+
|status                    |String                   |The state of the volume. |
|                          |                         |This will be             |
|                          |                         |``available`` when       |
|                          |                         |volume is created and    |
|                          |                         |ready for use.           |
+--------------------------+-------------------------+-------------------------+
|display_name              |String                   |The name assigned to the |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|attachments               |Array                    |An array of volume       |
|                          |                         |attachments.             |
+--------------------------+-------------------------+-------------------------+
|availabity_zone           |String                   |This parameter is no     |
|                          |                         |longer used and is       |
|                          |                         |always set to ``nova``.  |
+--------------------------+-------------------------+-------------------------+
|created_at                |Date                     |The date and time of     |
|                          |                         |volume creation.         |
+--------------------------+-------------------------+-------------------------+
|display_description       |String                   |The description for the  |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|image_id                  |String                   |The image_id use for the |
|                          |                         |volume. If no image was  |
|                          |                         |specified, this will be  |
|                          |                         |``null``.                |
+--------------------------+-------------------------+-------------------------+
|volume_type               |String                   |The type of volume,      |
|                          |                         |either ``SATA`` or       |
|                          |                         |``SSD``. Alternaltely,   |
|                          |                         |you can use the UUID     |
|                          |                         |volume id for the volume |
|                          |                         |instead of the name. The |
|                          |                         |default is ``SATA``.     |
+--------------------------+-------------------------+-------------------------+
|snapshot_id               |Uuid                     |The snapshot from which  |
|                          |                         |to create a volume, if   |
|                          |                         |any.                     |
+--------------------------+-------------------------+-------------------------+
|metadata                  |String                   |Any metadata for the     |
|                          |                         |volume.                  |
+--------------------------+-------------------------+-------------------------+
|id                        |String                   |The volume id.           |
+--------------------------+-------------------------+-------------------------+
|size                      |Integer                  |The size of the volume   |
|                          |                         |in gibibytes (GiB). The  |
|                          |                         |valid range for ``SATA`` |
|                          |                         |is 75-1024. The valid    |
|                          |                         |range for ``SSD`` is 50- |
|                          |                         |1024.                    |
+--------------------------+-------------------------+-------------------------+





**Example Retrieve list of volumes: JSON response**


.. code::

        Status Code: 200 OK
        Connection: keep-alive
        Content-Length: 435
        Content-Type: application/json
        Date: Wed, 10 Jun 2015 16:48:59 GMT
        X-Compute-Request-Id: req-292d0b03-6a35-4397-ac14-86081a7136c9


