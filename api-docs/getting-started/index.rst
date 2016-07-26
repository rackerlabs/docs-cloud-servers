.. _getting-started-guide:

===============
Getting started
===============

Use the following information to learn how to authenticate, send API requests,
and complete basic operations by using the |apiservice|.

For more information about Cloud Servers concepts and API operations, see the
:ref:`API Reference<api-reference>`.

.. note::

   If you are interested in learning how to get started with
   Orchestration using one of our SDKs, refer to
   :rax-devdocs:`Software development kits & tools <#sdks>`.


The exercises in this guide help you get started with the |apiservice|.

For each exercise in this guide, you choose one of the following methods to
make API calls:

-  The :how-to:`Nova Client<using-python-novaclient-with-the-rackspace-cloud>`.
   We recommend that you use the nova client to run simple commands that make
   API v2 calls. This open-source Python client runs on Linux or Mac OS X
   systems and is easy to learn and use. You can specify a debug parameter on
   any nova command to show the underlying API request for the command. This is
   a good way to become familiar with the API requests. For more information,
   see :ref:`Install CLI clients<install-CLI-client>`.

   ..  note::

       There is an optional
       `supernova client <https://github.com/major/supernova>`__, which is
       useful for managing multiple nova environments, but it is not supported.

-  `cURL <http://curl.haxx.se/>`__ commands. If you are familiar with or want
   to learn cURL commands, choose this method. With cURL, you send HTTP
   requests with embedded API v2 calls from the command line. The cURL examples
   in this guide include request bodies that are in JSON format. for more
   information, see :ref:`Using cURL<how-curl-commands-work>`.

To use this API, it helps to be familiar with HTTP/1.1, RESTful web services,
the |service| service, and the JSON data serialization format.



.. toctree::
   :maxdepth: 1

   get-credentials-include
   install-CLI-client
   send-request-ovw
   authenticate
   concepts
   Create your first Server <create-server-intro>
   Create your first network <create-network-intro>
   Attach your network to an existing server<attach-network-intro>


To start using the API and run the examples in this section, you need the
following items:

- Rackspace Cloud account. If you don't have one, sign up for a
  :rax-cart:`Rackspace Cloud account <cloud>`.
- :ref:`Command-line tool or browser client <send-api-requests>` for
  communicating with the API service.
- Environment variables configured for
  :ref:`cURL<configure-environment-variables>` or
  :ref:`nova client<install-CLI-client>` command line tool.