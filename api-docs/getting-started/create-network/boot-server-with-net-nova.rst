.. _boot-server-net-with-nova:

Boot server with network (nova client)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Issue the following nova client command:

.. code::  

   $ nova boot <name> --flavor <flavor> --image <image> --nic net-id=<private-net-uuid> 

**Positional arguments:**

-  ``name``. The name of the server.
-  ``flavor``. The flavor of the server.
-  ``image``. The image of the server.
-  ``--nic net-id=``. Creates a NIC on the server. Specify this option multiple times 
   to create multiple NICs.

If you do not specify any networks on the ``--nic`` parameter, PublicNet and 
ServiceNet are attached to your server.

.. note:: 
   
   ServiceNet is labeled as ``private`` and PublicNet is labeled as ``public`` in 
   the network list.

If you specify additional networks through the ``—nic`` parameter, these networks, in 
addition to PublicNet and ServiceNet, are attached to your server.

You can specify the optional ``--no-public`` and ``--no-service-net`` parameters to opt out 
of attaching PublicNet and ServiceNet to your server.

For example, you might issue the following command to attach a NIC to your server. 
Additionally, PublicNet and ServiceNet are attached to your server.

.. code::  

   $ nova boot my_server_with_network --flavor 2 --image d42f821e-c2d1-4796-9f07-af5ed7912d0e --nic net-id=e65accc0-1d98-45eb-af76-ab3d31edc7d2

The operation returns information about the new server, as shown in the following output:

.. code::  

   +-------------------------+--------------------------------------+
   | Property                | Value                                |
   +-------------------------+--------------------------------------+
   | OS-DCF:diskConfig       | AUTO                                 |
   | OS-EXT-STS:power_state  | 0                                    |
   | OS-EXT-STS:task_state   | scheduling                           |
   | OS-EXT-STS:vm_state     | building                             |
   | accessIPv4              |                                      |
   | accessIPv6              |                                      |
   | adminPass               | abababababab                         |
   | created                 | 2012-10-04T18:07:56Z                 |
   | flavor                  | 512MB Standard Instance              |
   | hostId                  |                                      |
   | id                      | 72859427-1e74-4a4f-b6b5-f547c1c3d452 |
   | image                   | Fedora 17 (Beefy Miracle)            |
   | metadata                | {}                                   |
   | name                    | my_server_with_network               |
   | progress                | 0                                    |
   | status                  | BUILD                                |
   | tenant_id               | 010101                               |
   | updated                 | 2012-10-04T18:07:56Z                 |
   | user_id                 | 170454                               |
   +-------------------------+--------------------------------------+

**Next topic:** :ref:`Get network details<get-network-details>`