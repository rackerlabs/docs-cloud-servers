.. _getting-server-details:

Getting server details
~~~~~~~~~~~~~~~~~~~~~~

Get details for your server to determine whether it built successfully.

The response for the get server details call shows the following information
for your server:

+-----------------------+----------------------------------------------------+
| Name                  | Description                                        |
+=======================+====================================================+
| OS-DCF:diskConfig     | The disk configuration value, which is ``AUTO`` or |
|                       | ``MANUAL``.                                        |
+-----------------------+----------------------------------------------------+
| OS-EXT-STS:power\_sta | Extended attribute. The power state.               |
| te                    |                                                    |
+-----------------------+----------------------------------------------------+
| OS-EXT-STS:task\_stat | The task state.                                    |
| e                     |                                                    |
+-----------------------+----------------------------------------------------+
| OS-EXT-STS:vm\_state  | The VM state.                                      |
+-----------------------+----------------------------------------------------+
| created               | The time stamp for when the server was created.    |
+-----------------------+----------------------------------------------------+
| flavor                | The flavor ID and links.                           |
+-----------------------+----------------------------------------------------+
| hostId                | The host ID.                                       |
+-----------------------+----------------------------------------------------+
| id                    | The server ID.                                     |
+-----------------------+----------------------------------------------------+
| image                 | The image name.                                    |
+-----------------------+----------------------------------------------------+
| metadata              | Any metadata key and value pairs.                  |
+-----------------------+----------------------------------------------------+
| name                  | The server name.                                   |
+-----------------------+----------------------------------------------------+
| private network       | Your private IP address.                           |
+-----------------------+----------------------------------------------------+
| public network        | The public IP address. Use this address to log     |
|                       | into the server.                                   |
+-----------------------+----------------------------------------------------+
| status                | The server status. A status of ``ACTIVE``          |
|                       | indicates that your server built successfully and  |
|                       | is active.                                         |
+-----------------------+----------------------------------------------------+
| progress              | The percentage value of the build status. For      |
|                       | example, if the status is ``BUILD`` and the        |
|                       | progress is ``60``, the server is 60% built.       |
+-----------------------+----------------------------------------------------+


The sections are also organized by example type. To simplify your path through
this topic, decide whether you prefer neutron-client or cURL examples.


**Next step:** Choose one of the following methods:

.. toctree::
   :maxdepth: 2

   getting-server-details-nova
   getting-server-details-curl