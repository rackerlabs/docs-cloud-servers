.. _nc-sa-ssh:

SSH into a server
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


SSH into a server.

**Usage:**

.. code::  

    $ nova ssh [--port PORT] [--private] [--ipv6] [--login <login>] [-i IDENTITY] <server>

**Positional argument:**

-  ``server``. The name or ID of the server that you want to SSH into.

**Optional arguments:**

-  ``--port`` ``PORT``. Optional flag that indicates which port to use for ssh. Default=22.

-  ``--private``. Optional flag that indicates whether to use private address attached to 
   an instance. Default=False.

-  ``--ipv6``. Optional flag that indicates whether to use an IPv6 address attached to an 
   instance. Defaults to the IPv4 address.

-  ``--login`` ``login``. The login to use.

-  ``-i`` ``IDENTITY``, ``--identity`` ``IDENTITY``. The private key file, same as the 
   ß``-i`` option to the **ssh** command.

**Output**: None.
