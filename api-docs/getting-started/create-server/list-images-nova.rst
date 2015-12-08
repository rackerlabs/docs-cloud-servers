.. _list-images-with-nova:

List images (nova client)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#. Issue the following command.

   **List images with nova request**

   .. code::  

       $ nova image-list

   The operation returns the image ID, name, and status, as shown in the following output.
   
   **List images with nova response**

   .. code::  

       +--------------------------------------+-----------------------------------------------------------------------------+--------+--------+
       | ID                                   | Name                                                                        | Status | Server |
       +--------------------------------------+-----------------------------------------------------------------------------+--------+--------+
       | 0d589460-f177-4b0f-81c1-8ab8903ac7d8 | Arch 2011.10                                                                | ACTIVE |        |
       | 03318d19-b6e6-4092-9b5c-4758ee0ada60 | CentOS 5.6                                                                  | ACTIVE |        |
       | a3a2c42f-575f-4381-9c6d-fcd3b7d07d17 | CentOS 6.0                                                                  | ACTIVE |        |
       | 0cab6212-f231-4abd-9c70-608d0d0e04ba | CentOS 6.2                                                                  | ACTIVE |        |
       | c195ef3b-9195-4474-b6f7-16e5bd86acd0 | CentOS 6.3                                                                  | ACTIVE |        |
       | a10eacf7-ac15-4225-b533-5744f1fe47c1 | Debian 6 (Squeeze)                                                          | ACTIVE |        |
       | bca91446-e60e-42e7-9e39-0582e7e20fb9 | Fedora 16 (Verne)                                                           | ACTIVE |        |
       | d42f821e-c2d1-4796-9f07-af5ed7912d0e | Fedora 17 (Beefy Miracle)                                                   | ACTIVE |        |
       | c79fecf7-2c37-4c51-a240-e9fa913c90a3 | FreeBSD 9                                                                   | ACTIVE |        |
       | 040e6c82-6618-4f53-9f27-44db2c4ce9ee | Gentoo 11.0                                                                 | ACTIVE |        |
       | 644be485-411d-4bac-aba5-5f60641d92b5 | Red Hat Enterprise Linux 5.5                                                | ACTIVE |        |
       | d6dd6c70-a122-4391-91a8-decb1a356549 | Red Hat Enterprise Linux 6.1                                                | ACTIVE |        |
       | d531a2dd-7ae9-4407-bb5a-e5ea03303d98 | Ubuntu 10.04 LTS (Lucid Lynx)                                               | ACTIVE |        |
       | 8bf22129-8483-462b-a020-1754ec822770 | Ubuntu 11.04 (Natty Narwhal)                                                | ACTIVE |        |
       | 3afe97b2-26dc-49c5-a2cc-a2fc8d80c001 | Ubuntu 11.10 (Oneiric Oncelot)                                              | ACTIVE |        |
       | 5cebb13a-f783-4f8c-8058-c4182c724ccd | Ubuntu 12.04 LTS (Precise Pangolin)                                         | ACTIVE |        |
       | b9ea8426-8f43-4224-a182-7cdb2bb897c8 | Windows Server 2008 R2 SP1                                                  | ACTIVE |        |
       | 7957e53d-b3b9-41fe-8e0d-5252bf20a5bf | Windows Server 2008 R2 SP1 (with updates)                                   | ACTIVE |        |
       | 535d5453-79dd-4635-bbd6-d87b1f1cd717 | Windows Server 2008 R2 SP1 (with updates) + SQL Server 2008 R2 SP1 Standard | ACTIVE |        |
       | 80599479-b5a2-49f2-bb46-2bc75a8be98b | Windows Server 2008 R2 SP1 (with updates) + SQL Server 2008 R2 SP1 Web      | ACTIVE |        |
       | e4589dc6-b972-482f-91ef-67feb891b559 | Windows Server 2008 R2 SP1 (with updates) + SQL Server 2012 Standard        | ACTIVE |        |
       | 6f8ab5a1-42ff-433b-be40-e17374f2fff4 | Windows Server 2008 R2 SP1 (with updates) + SQL Server 2012 Web             | ACTIVE |        |
       | 2a4a02aa-523a-4649-9802-3a09de8e5f1b | Windows Server 2008 R2 SP1 + SQL Server 2008 R2 Standard                    | ACTIVE |        |
       | d6153e86-f4e0-4053-a711-d35632e512cd | Windows Server 2008 R2 SP1 + SQL Server 2008 R2 Web                         | ACTIVE |        |
       | f7d06722-2b30-4c02-b74d-da5a7337f357 | Windows Server 2008 R2 SP1 + SQL Server 2012 Standard                       | ACTIVE |        |
       | e7a11eed-d348-44da-8210-f136d4256e81 | Windows Server 2008 R2 SP1 + SQL Server 2012 Web                            | ACTIVE |        |
       | 096c55e5-39f3-48cf-a413-68d9377a3ab6 | openSUSE 12.1                                                               | ACTIVE |        |
       +--------------------------------------+-----------------------------------------------------------------------------+--------+--------+

#. Copy the image ID for you desired image from the ``ID`` field in the
   output.

   In this example, use the ``ID`` value for the Ubuntu 11.10 image,
   which is ``3afe97b2-26dc-49c50a2cc-a2fc8d80c001``.

**Next topic:** :ref:`List flavors<list-flavors>` 

