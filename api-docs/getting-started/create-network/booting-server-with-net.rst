.. _booting-server-with-net:

Booting server with an isolated network
---------------------------------------

To create your new server and attach an isolated network, you need the
following information:

- The name of the new server. Use a name of your choice.
- The image ID, from :ref:`Listing images<listing-images>`.
- The flavor ID, from :ref:`Listing flavors<listing-flavors>`.
- The network ID of your isolated network from :ref:`Creating network<creating-network>`.

The sections are also organized by example type. To simplify your path through
this topic, decide whether you prefer nova client or cURL examples.

**Next step:** Choose one of the following methods:

.. toctree::
   :maxdepth: 2

   booting-server-with-net-nova
   booting-server-with-net-curl