.. _boot-server-with-net:

Booting server with an isolated network
---------------------------------------

To create your new server and attach an isolated network, you need the following information:

- The name of the new server. Use a name of your choice.
- The image ID, from :ref:`List images<list-images>`.
- The flavor ID, from :ref:`List flavors<list-flavors>`.
- The network ID of your isolated network from :ref:`Create network<create-network>`.

The sections are also organized by example type. To simplify your path through this 
topic, decide whether you prefer nova client or cURL examples.

**Next step:** Choose one of the following methods:

-  :ref:`Boot server with network with nova client <boot-server-net-with-nova>`
-  :ref:`Boot server with network with cURL <boot-server-net-with-curl>`

.. toctree::
   :maxdepth: 2
   
   boot-server-with-net-nova
   boot-server-with-net-curl