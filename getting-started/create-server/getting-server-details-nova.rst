.. _getting-server-details-with-nova:

Getting server details (nova client)
------------------------------------

#. Issue the following command.

**Get server details with nova request**

   .. code::

       $ nova show <id>

   Where ``id`` is the server ID that you copied in
   :ref:`Booting server (nova client)<booting-server-with-nova>`.

   The command shows information for your server, including its private and
   public IP addresses, and status.

   **Get server details with nova response**

   .. code::

       +-------------------------+------------------------------------------------------------------------------------------------------------------+
       | Property                | Value                                                                                                            |
       +-------------------------+------------------------------------------------------------------------------------------------------------------+
       | OS-DCF:diskConfig       | AUTO                                                                                                             |
       | OS-EXT-STS:power_state  | 1                                                                                                                |
       | OS-EXT-STS:task_state   | None                                                                                                             |
       | OS-EXT-STS:vm_state     | active                                                                                                           |
       | accessIPv4              | 198.101.231.59                                                                                                   |
       | accessIPv6              | 2001:4800:780d:0509:d87b:9cbc:ff04:488b                                                                          |
       | created                 | 2012-08-16T16:28:18Z                                                                                             |
       | flavor                  | 8GB Standard Instance (6)                                                                                        |
       | hostId                  | d934ece70c2df646ee9fa45958d254819c46dfe244c51f880224b8f2                                                         |
       | id                      | 9da98125-0de8-4b84-880c-b42977c32773                                                                             |
       | image                   | Ubuntu 11.10 (Oneiric Oncelot) (3afe97b2-26dc-49c5-a2cc-a2fc8d80c001)                                            |
       | metadata                | {}                                                                                                               |
       | name                    | myUbuntuServer                                                                                                   |
       | private network         | 10.179.224.74                                                                                                    |
       | progress                | 100                                                                                                              |
       | public network          | 2001:4800:780d:0509:d87b:9cbc:ff04:488b, 198.101.231.59                                                          |
       | status                  | ACTIVE                                                                                                           |
       | tenant_id               | 010101                                                                                                           |
       | updated                 | 2012-08-16T16:32:48Z                                                                                             |
       | user_id                 | 170454                                                                                                           |
       +-------------------------+------------------------------------------------------------------------------------------------------------------+

2. Run the command until the status of your server is ``ACTIVE``. Typically,
   servers take a few minutes to build.

3. Copy the public IP address that is returned for your server from the
   ``public network`` field. You use this address when you log into your
   server.

**Next topic:** :ref:`Listing servers<listing-servers>`

