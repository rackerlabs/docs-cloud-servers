.. _listing-flavors-with-nova:

Listing flavors (nova client)
-----------------------------

#. Issue the following command.

   **List flavors with nova request**

   .. code::

       $ nova flavor-list

   Optional parameter: ``--extra-specs``, shows details including class, disk
   I/O, and the number of data disks.

   The operation returns details that describes each flavor, as shown the
   following example.

   **List flavors with nova response**

   .. code::

                                                             Flavor List
       +------------------+-------------------------+-----------+------+-----------+------+-------+-------------+-----------+
       | ID               | Name                    | Memory_MB | Disk | Ephemeral | Swap | VCPUs | RXTX_Factor | Is_Public |
       +------------------+-------------------------+-----------+------+-----------+------+-------+-------------+-----------+
       | 2                | 512MB Standard Instance | 512       | 20   | 0         | 512  | 1     | 80.0        | N/A       |
       | 3                | 1GB Standard Instance   | 1024      | 40   | 0         | 1024 | 1     | 120.0       | N/A       |
       | 4                | 2GB Standard Instance   | 2048      | 80   | 0         | 2048 | 2     | 240.0       | N/A       |
       | 5                | 4GB Standard Instance   | 4096      | 160  | 0         | 2048 | 2     | 400.0       | N/A       |
       | 6                | 8GB Standard Instance   | 8192      | 320  | 0         | 2048 | 4     | 600.0       | N/A       |
       | 7                | 15GB Standard Instance  | 15360     | 620  | 0         | 2048 | 6     | 800.0       | N/A       |
       | 8                | 30GB Standard Instance  | 30720     | 1200 | 0         | 2048 | 8     | 1200.0      | N/A       |
       | compute1-15      | 15 GB Compute v1        | 15360     | 0    | 0         |      | 8     | 1250.0      | N/A       |
       | compute1-30      | 30 GB Compute v1        | 30720     | 0    | 0         |      | 16    | 2500.0      | N/A       |
       | compute1-4       | 4 GB Compute v1         | 3840      | 0    | 0         |      | 2     | 312.5       | N/A       |
       | compute1-60      | 60 GB Compute v1        | 61440     | 0    | 0         |      | 32    | 5000.0      | N/A       |
       | compute1-8       | 8 GB Compute v1         | 7680      | 0    | 0         |      | 4     | 625.0       | N/A       |
       | general1-1       | 1 GB General Purpose v1 | 1024      | 20   | 0         |      | 1     | 200.0       | N/A       |
       | general1-2       | 2 GB General Purpose v1 | 2048      | 40   | 0         |      | 2     | 400.0       | N/A       |
       | general1-4       | 4 GB General Purpose v1 | 4096      | 80   | 0         |      | 4     | 800.0       | N/A       |
       | general1-8       | 8 GB General Purpose v1 | 8192      | 160  | 0         |      | 8     | 1600.0      | N/A       |
       | io1-120          | 120 GB I/O v1           | 122880    | 40   | 1200      |      | 32    | 10000.0     | N/A       |
       | io1-15           | 15 GB I/O v1            | 15360     | 40   | 150       |      | 4     | 1250.0      | N/A       |
       | io1-30           | 30 GB I/O v1            | 30720     | 40   | 300       |      | 8     | 2500.0      | N/A       |
       | io1-60           | 60 GB I/O v1            | 61440     | 40   | 600       |      | 16    | 5000.0      | N/A       |
       | io1-90           | 90 GB I/O v1            | 92160     | 40   | 900       |      | 24    | 7500.0      | N/A       |
       | memory1-120      | 120 GB Memory v1        | 122880    | 0    | 0         |      | 16    | 5000.0      | N/A       |
       | memory1-15       | 15 GB Memory v1         | 15360     | 0    | 0         |      | 2     | 625.0       | N/A       |
       | memory1-240      | 240 GB Memory v1        | 245760    | 0    | 0         |      | 32    | 10000.0     | N/A       |
       | memory1-30       | 30 GB Memory v1         | 30720     | 0    | 0         |      | 4     | 1250.0      | N/A       |
       | memory1-60       | 60 GB Memory v1         | 61440     | 0    | 0         |      | 8     | 2500.0      | N/A       |
       | performance1-1   | 1 GB Performance        | 1024      | 20   | 0         |      | 1     | 200.0       | N/A       |
       | performance1-2   | 2 GB Performance        | 2048      | 40   | 20        |      | 2     | 400.0       | N/A       |
       | performance1-4   | 4 GB Performance        | 4096      | 40   | 40        |      | 4     | 800.0       | N/A       |
       | performance1-8   | 8 GB Performance        | 8192      | 40   | 80        |      | 8     | 1600.0      | N/A       |
       | performance2-120 | 120 GB Performance      | 122880    | 40   | 1200      |      | 32    | 10000.0     | N/A       |
       | performance2-15  | 15 GB Performance       | 15360     | 40   | 150       |      | 4     | 1250.0      | N/A       |
       | performance2-30  | 30 GB Performance       | 30720     | 40   | 300       |      | 8     | 2500.0      | N/A       |
       | performance2-60  | 60 GB Performance       | 61440     | 40   | 600       |      | 16    | 5000.0      | N/A       |
       | performance2-90  | 90 GB Performance       | 92160     | 40   | 900       |      | 24    | 7500.0      | N/A       |
       +------------------+-------------------------+-----------+------+-----------+------+-------+-------------+-----------+


#. Copy the ID of the flavor you want to use from the ``ID`` field in the
   output.

   In this example, use the flavor ID for the 8GB Standard Instance, which is
   ``6``.

**Next topic:**  :ref:`Booting server<booting-server>`

