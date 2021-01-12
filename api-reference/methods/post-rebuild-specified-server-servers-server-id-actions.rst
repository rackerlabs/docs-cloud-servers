.. _post-rebuild-specified-server-servers-server-id-actions:

Rebuild specified server
------------------------

.. code::

    POST /servers/{server_id}/action

This operation rebuilds the specified server.

The rebuild operation removes all data on the server and replaces it with the
specified image. The serverID and all IP addresses remain the same. If you
specify name, metadata, accessIPv4, or accessIPv6 in the rebuild request, new
values replace existing values. Otherwise, these values do not change. You can
inject data into the file system during the rebuild.

.. note::
   This operation is not available for OnMetal servers.

Specify the target server ID in the URI.

In the request body, specify the rebuild action followed by various attributes,
listed in the following parameters section.


This table shows the possible response codes for this operation:

+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|202                      |Success                  |Request succeeded.       |
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

This table shows the URI parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+

This table shows the body parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**rebuild**               |Object                  |Specification of the     |
|                          |                        |rebuild action for the   |
|                          |                        |specified server.        |
+--------------------------+------------------------+-------------------------+
|rebuild.\ **name**        |Object *(Optional)*     |The new name for the     |
|                          |                        |server.                  |
+--------------------------+------------------------+-------------------------+
|rebuild.\ **imageRef**    |Object                  |The image ID.            |
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|rebuild.\ **accessIPv4**  |Object *(Optional)*     |The IP version 4 address.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|rebuild.\ **accessIPv6**  |Object *(Optional)*     |The IP version 6 address.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|rebuild.\ **adminPass**   |String *(Optional)*     |The password assigned to |
|                          |                        |provide login access to  |
|                          |                        |the server.              |
+--------------------------+------------------------+-------------------------+
|rebuild.\ **metadata**    |String *(Optional)*     |A metadata key and value |
|                          |                        |pair.                    |
+--------------------------+------------------------+-------------------------+
|rebuild.\ **personality** |String *(Optional)*     |The file path and file   |
|                          |                        |contents.                |
+--------------------------+------------------------+-------------------------+
|rebuild.\ **OS-           |String *(Optional)*     |The disk configuration   |
|DCF:diskConfig**          |                        |value. Valid values are: |
|                          |                        |AUTO:The server is built |
|                          |                        |with a single partition  |
|                          |                        |which is the size of the |
|                          |                        |target flavor disk. The  |
|                          |                        |file system is           |
|                          |                        |automatically adjusted   |
|                          |                        |to fit the entire        |
|                          |                        |partition. This keeps    |
|                          |                        |things simple and        |
|                          |                        |automated. AUTO is valid |
|                          |                        |only for images and      |
|                          |                        |servers with a single    |
|                          |                        |partition that use the   |
|                          |                        |EXT3 file system. This   |
|                          |                        |is the default setting   |
|                          |                        |for applicable Rackspace |
|                          |                        |base images. MANUAL:The  |
|                          |                        |server is built using    |
|                          |                        |the partition scheme and |
|                          |                        |file system of the       |
|                          |                        |source image. If the     |
|                          |                        |target flavor disk is    |
|                          |                        |larger, the remaining    |
|                          |                        |disk space is left       |
|                          |                        |unpartitioned. This      |
|                          |                        |enables images to have   |
|                          |                        |non-EXT3 file systems,   |
|                          |                        |multiple partitions, and |
|                          |                        |so on, and it enables    |
|                          |                        |you to manage the disk   |
|                          |                        |configuration.           |
+--------------------------+------------------------+-------------------------+

**Example Rebuild specified server: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "rebuild" :{
           "name" : "new-server-test",
           "imageRef" : "d42f821e-c2d1-4796-9f07-af5ed7912d0e",
           "OS-DCF:diskConfig" : "AUTO",
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


Response
^^^^^^^^


This table shows the body parameters for the response:

+---------------------------+------------------------+------------------------+
|Name                       |Type                    |Description             |
+===========================+========================+========================+
|**server**                 |Object                  |The container for       |
|                           |                        |server data.            |
+---------------------------+------------------------+------------------------+
|server.\ **id**            |Uuid                    |The ID of the server.   |
+---------------------------+------------------------+------------------------+
|server.\ **links**         |Uuid                    |An array of the self    |
|                           |                        |and bookmark links to   |
|                           |                        |the server.             |
+---------------------------+------------------------+------------------------+
|server.links.\  **href**   |Uuid                    |The URL for the server  |
|                           |                        |and the associated      |
|                           |                        |``rel``.                |
+---------------------------+------------------------+------------------------+
|server.links.\ **rel**     |Uuid                    |The descriptive field   |
|                           |                        |for the associated      |
|                           |                        |``href``, which is      |
|                           |                        |either ``self`` or      |
|                           |                        |``bookmark``.           |
+---------------------------+------------------------+------------------------+
|server.\  **adminPass**    |String                  |The password assigned   |
|                           |                        |to provide login access |
|                           |                        |to the server.          |
+---------------------------+------------------------+------------------------+
|server.\ **OS-             |String                  |The disk configuration  |
|DCF:diskConfig**           |                        |value. Valid values are |
|                           |                        |``AUTO`` and ``MANUAL``.|
+---------------------------+------------------------+------------------------+


**Example Rebuild specified server: JSON response**


.. code::

       Status Code: 202 OK
       Content-Length: 1250
       Content-Type: application/json
       Date: Thu, 04 Dec 2014 19:41:58 GMT
       Server: Jetty(8.0.y.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/2.12)
       x-compute-request-id: req-8c905dfe-2c9a-42d9-8e53-4478e2813c75


.. code::

   {
       "server": {
           "OS-DCF:diskConfig": "AUTO",
           "accessIPv4": "50.56.175.199",
           "accessIPv6": "2001:4800:780e:0510:d87b:9cbc:ff04:35f7",
           "addresses": {
               "private": [
                   {
                       "addr": "10.180.12.68",
                       "version": 4
                   }
               ],
               "public": [
                   {
                       "addr": "2001:4800:780e:0510:d87b:9cbc:ff04:35f7",
                       "version": 6
                   },
                   {
                       "addr": "50.56.175.199",
                       "version": 4
                   }
               ]
           },
           "adminPass": "diane123",
           "config_drive": "",
           "created": "2012-07-23T20:20:04Z",
           "flavor": {
               "id": "6",
               "links": [
                   {
                       "href": "https://dfw.servers.api.rackspacecloud.com/123456/flavors/6",
                       "rel": "bookmark"
                   }
               ]
           },
           "hostId": "791b847459d001f02f65f23ea82ae32c4b320ad34a3f892b7593c01f",
           "id": "32406068-8539-40ab-bdd3-8140d30823ad",
           "image": {
               "id": "d42f821e-c2d1-4796-9f07-af5ed7912d0e",
               "links": [
                   {
                       "href": "https://dfw.servers.api.rackspacecloud.com/123456/images/d42f821e-c2d1-4796-9f07-af5ed7912d0e",
                       "rel": "bookmark"
                   }
               ]
           },
           "links": [
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/v2/123456/servers/32406068-8539-40ab-bdd3-8140d30823ad",
                   "rel": "self"
               },
               {
                   "href": "https://dfw.servers.api.rackspacecloud.com/123456/servers/32406068-8539-40ab-bdd3-8140d30823ad",
                   "rel": "bookmark"
               }
           ],
           "metadata": {
               "My Server Name": "Apache1"
           },
           "name": "new-server-test",
           "progress": 0,
           "status": "REBUILD",
           "tenant_id": "123456",
           "updated": "2012-07-26T16:09:16Z",
           "user_id": "170454"
       }
   }




