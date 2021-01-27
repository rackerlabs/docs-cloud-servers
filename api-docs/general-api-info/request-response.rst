.. _req-resp-types:

==========================
Request and response types
==========================

The |apiservice| supports JSON data serialization request and response format.

The request format is specified by using the ``Content-Type`` header and is
required for operations that have a request body. This header is required for
operations that have a request body. The syntax for the ``Content-Type``
header is:

.. code::

    Content-Type: application/format

Where ``format`` is ``json``.

The response format is specified by using one of the following methods:

-  ``Accept`` header. The syntax for the ``Accept`` header is::

       Accept: application/format

   Where ``format`` is ``json``.

-  Query extension. Add the ``.json`` extension to the
   request URI. For example, the ``.json`` extension in the following URI
   request specifies that the response body is returned in JSON format:

   .. code::

      POST /v2/010101/servers.json

If you do not specify a response format, JSON is the default.
