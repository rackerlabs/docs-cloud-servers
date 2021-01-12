.. _booting-server-with-nova:

Booting server (nova client)
----------------------------

#. Issue the following command. In the command, specify the server name, flavor
   ID, and image ID. You may optionally include the keypair name.

   **Boot a server with nova request**

   .. code::

       $ nova boot myUbuntuServer --image "3afe97b2-26dc-49c5-a2cc-a2fc8d80c001" \
         --flavor 6 --key-name myKey --config-drive true

   For more information about keypairs, see
   :ref:`Create a server key pair<post-create-a-server-key-pair-os-keypairs>`.

   The command returns a list of server properties. The status field indicates
   whether the server is being built or is active. A status of ``BUILD``
   indicates that your server is being built.

   **Boot a server with nova response**

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
       | adminPass               | j3Peu626UnDJ                         |
       | created                 | 2012-08-16T16:28:13Z                 |
       | flavor                  | 8GB Standard Instance                |
       | hostId                  |                                      |
       | id                      | 9da98125-0de8-4b84-880c-b42977c32773 |
       | image                   | Ubuntu 11.10 (Oneiric Oncelot)       |
       | metadata                | {}                                   |
       | name                    | myUbuntuServer                       |
       | progress                | 0                                    |
       | status                  | BUILD                                |
       | tenant_id               | 010101                               |
       | updated                 | 2012-08-16T16:28:14Z                 |
       | user_id                 | 170454                               |
       +-------------------------+--------------------------------------+

#. Copy the server ID value from the ``id`` field in the output. You use this
   ID to get details for your server to determine if it built successfully.

   Copy the administrative password value from the ``adminPass`` field. You use
   this value to log into your server.

**Next topic:** :ref:`Getting server details<getting-server-details>`
