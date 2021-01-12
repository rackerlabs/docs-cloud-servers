.. _listing-images-with-nova:

Listing images (nova client)
----------------------------

#. Issue the following command.

   **List images with nova request**

   .. code::

       $ nova image-list

   The operation returns the image ID, name, and status, as shown in the
   following output.

   **List images with nova response**

   .. code::

       +--------------------------------------+-----------------------------------------------------------------------------+--------+--------+
       | ID                                   | Name                                                                        | Status | Server |
       +--------------------------------------+-----------------------------------------------------------------------------+--------+--------+
       | a77d07e9-289d-427a-a5ae-465c894c5232 | CentOS 6 (PVHVM)                                                            | ACTIVE |        |
       | d8fb8833-2835-4a9b-9536-6e93845dee37 | CentOS 7 (PVHVM)                                                            | ACTIVE |        |
       | 4fed5350-f0ab-4090-a03b-ed9a3e7b4dd4 | CentOS 7 (PVHVM) (Orchestration)                                            | ACTIVE |        |
       | b3aecd49-225e-4128-b9d6-c056aa025dbc | CentOS 8 (PVHVM)                                                            | ACTIVE |        |
       | ea6a268d-2e72-4a96-bd4a-c10eeeae1b77 | Debian 10 (Buster) (PVHVM)                                                  | ACTIVE |        |
       | f3a636cf-ff70-4765-8339-6a17bf35ef21 | Debian 9 (Stretch) (PVHVM)                                                  | ACTIVE |        |
       | d0bf118f-6bd1-4ddd-9748-b62cb8edd133 | Debian 9 (Stretch) (PVHVM) (Orchestration)                                  | ACTIVE |        |
       | 13c9b4ac-b50e-47ea-aa73-b23c4083bf05 | Fedora 30 (PVHVM)                                                           | ACTIVE |        |
       | afa8d856-eec2-4f23-bff5-da88eff0983b | Fedora 31 (PVHVM)                                                           | ACTIVE |        |
       | ccbbb8bb-b2f5-4283-91af-58c86923a279 | Fedora 32 (PVHVM)                                                           | ACTIVE |        |
       | 0c3c74be-b17e-477c-b9d6-438f492ca25b | Fortigate-VM 6.2                                                            | ACTIVE |        |
       | 9aa0d346-c06f-4652-bbb1-4342a7d2d017 | iPXE Boot (boot.rackspace.com)                                              | ACTIVE |        |
       | f8c7ce92-54e2-4669-ad84-f242fb54f489 | OnMetal - CentOS 6                                                          | ACTIVE |        |
       | 80418aa9-c965-4a9f-8d32-828e656076bf | OnMetal - CentOS 7                                                          | ACTIVE |        |
       | 4b7af476-acba-4051-b134-e64c90f0df65 | OnMetal - Debian 9 (Stretch)                                                | ACTIVE |        |
       | 563929f6-4b68-4b1f-8403-d2371e78d913 | OnMetal - Ubuntu 20.02 LTS (Focal Fossa)                                    | ACTIVE |        |
       | edf186d0-7c23-46ee-be7b-c2285159f572 | OnMetal - Windows Server 2012 R2                                            | ACTIVE |        |
       | f7813dc7-246e-42c9-b85b-5e0b8c05c2f8 | OnMetal - Windows Server 2012 R2 + SQL 2014 Standard                        | ACTIVE |        |
       | 535d5453-79dd-4635-bbd6-d87b1f1cd717 | OnMetal - Windows Server 2012 R2 + SQL 2014 Web                             | ACTIVE |        |
       | 93deda76-bd77-471c-8671-122ca1fb2fc4 | OnMetal - Windows Server 2016                                               | ACTIVE |        |
       | bebecb24-92ce-47b0-ae4d-943056530df3 | OnMetal - Windows Server 2016 + SQL 2016 Standard                           | ACTIVE |        |
       | 13aadf3a-0d41-4393-9f70-0fb162a70bfa | OnMetal - Windows Server 2016 + SQL 2016 Web                                | ACTIVE |        |
       | 030b2661-fba0-4293-833c-110b2f1677e5 | OnMetal - Windows Server 2016 + SQL 2019 Standard                           | ACTIVE |        |
       | 4471b1ac-ab03-4c1c-ad01-0617c477cacd | OnMetal - Windows Server 2016 + SQL 2019 Web                                | ACTIVE |        |
       | f4ab861d-6d51-4721-b200-032cf3b7ddf8 | OnMetal - Windows Server 2019                                               | ACTIVE |        |
       | b85f3ce7-2f74-441c-a03a-20d789fba95c | OnMetal - Windows Server 2019 + SQL 2019 Standard                           | ACTIVE |        |
       | bafec370-a272-4f18-8e42-7db5d585cb56 | OnMetal - Windows Server 2019 + SQL 2019 Web                                | ACTIVE |        |
       | 8c60a26b-dfdb-4d16-b281-732f03550cbb | Ubuntu 16.04 LTS (Xenial Xerus) (Cloud)                                     | ACTIVE |        |
       | 5a0422c0-628e-41c8-8084-95ef80a943d6 | Ubuntu 18.04 LTS (Bionic Beaver) (Cloud)                                    | ACTIVE |        |
       | 5276ee58-b33b-43ab-be4f-427270477bee | Ubuntu 20.04 LTS (Focal Fossa) (Cloud)                                      | ACTIVE |        |
       | 840a63ef-025d-49bd-96d5-54a114880188 | Windows Server 2012 R2                                                      | ACTIVE |        |
       | ae97b51e-91ef-43a3-86ce-59a91312fc1c | Windows Server 2012 R2 + SQL Server 2014 Standard                           | ACTIVE |        |
       | aa538f9e-f8f6-43a2-84ad-687ee48708a7 | Windows Server 2012 R2 + SQL Server 2014 Web                                | ACTIVE |        |
       | d3a04d8d-59a0-4e8d-87e6-4d02f840380a | Windows Server 2012 R2 + SQL Server 2016 Standard                           | ACTIVE |        |
       | 0a05ae4f-305d-4810-aa6a-965d51235e0a | Windows Server 2012 R2 + SQL Server 2016 Web                                | ACTIVE |        |
       | abdefd26-044a-4747-a942-0c26b06633ba | Windows Server 2012 R2 + SQL Server 2017 Standard                           | ACTIVE |        |
       | cc157b88-d97e-40d2-807b-0e3c16e180e9 | Windows Server 2012 R2 + SQL Server 2017 Web                                | ACTIVE |        |
       | 59b2a8c5-e947-4430-8bfd-740a24929d77 | Windows Server 2016                                                         | ACTIVE |        |
       | 91e1116c-2186-4a74-be13-3c6abd85084b | Windows Server 2016 + SQL Server 2019 Standard                              | ACTIVE |        |
       | 0b0b0ca9-cb58-4ade-a125-88815157d73b | Windows Server 2016 + SQL Server 2019 Web                                   | ACTIVE |        |
       | 28fd2fba-67bc-4884-a2ef-d6dbd95440a8 | Windows Server 2019                                                         | ACTIVE |        |
       | 0696f7ec-c5aa-4f4b-baf9-450c1581e01a | Windows Server 2019 + SQL Server 2019 Standard                              | ACTIVE |        |
       | 95d949bd-b8ab-4432-8cc0-b680aecb35a3 | Windows Server 2019 + SQL Server 2019 Web                                   | ACTIVE |        |
       +--------------------------------------+-----------------------------------------------------------------------------+--------+--------+

#. Copy the image ID for your desired image from the ``ID`` field in the
   output.

   In this example, use the ``ID`` value for the Ubuntu 11.10 image,
   which is ``3afe97b2-26dc-49c50a2cc-a2fc8d80c001``.

**Next topic:** :ref:`Listing flavors<listing-flavors>`
