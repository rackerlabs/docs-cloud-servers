.. _nc-list-hosts:

List hosts
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists all hosts by service.

**Usage:**

.. code::  

    $ nova host-list

**Output:**

.. code::  

    +-----------------------------------------------+-------------+
    | host_name                                     | service     |
    +-----------------------------------------------+-------------+
    | nova-cells01-r3040.c0002.dfw.ohthree.com      | cells       |
    | nova-cells01-r3040.global.dfw.ohthree.com     | cells       |
    | nova-cells02-r3040.global.dfw.ohthree.com     | cells       |
    | nova-console01-r3040.global.dfw.ohthree.com   | consoleauth |
    | nova-network01-r3040.global.dfw.ohthree.com   | network     |
    | nova-network02-r3040.c0002.dfw.ohthree.com    | network     |
    | nova-network02-r3040.global.dfw.ohthree.com   | network     |
    | nova-scheduler01-r3040.c0002.dfw.ohthree.com  | scheduler   |
    | nova-scheduler01-r3040.global.dfw.ohthree.com | scheduler   |
    | volume-api01-r3040.global.dfw.ohthree.com     | volume      |
    +-----------------------------------------------+-------------+
