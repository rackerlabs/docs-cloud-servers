.. _getting-started:

Getting Started Guide
-----------------------

Use this *Getting Started Guide* to learn how to authenticate, send API requests, 
and complete basic operations by using the |apiservice|.

For more information about Cloud Servers concepts and API operations, see the 
:ref:`Developer Guide<developer-guide>` and the :ref:`API Reference<api-reference>`. 

.. note::

   If you are interested in learning how to get started with
   Orchestration using one of our SDKs, refer to
   :rax-devdocs:`Software development kits & tools <#sdks>`.
   
   
The simple exercises in this guide help you get started with the |apiservice|.

For each exercise in this guide, you choose one of the following methods to make API calls:

-  The :kc-article:`Nova Client<using-python-novaclient-with-the-rackspace-cloud>`.
   We recommend that you use the nova client to run simple commands that make API v2 calls. 
   This open-source Python client runs on Linux or Mac OS X systems and is easy to learn 
   and use. You can specify a debug parameter on any nova command to show the underlying API 
   request for the command. This is a good way to become familiar with the API requests.
   For more information, see :ref:`Using the nova client<request-using-nova-client>`.

   ..  note:: 

       There is an optional `supernova client <https://github.com/major/supernova>`__, 
       which is useful for managing multiple nova environments, but it is not supported.

-  `cURL <http://curl.haxx.se/>`__ commands. If you are familiar with or want to learn 
   cURL commands, choose this method. With cURL, you send HTTP requests with embedded API 
   v2 calls from the command line. The cURL examples in this guide include request bodies 
   that are in JSON format. for more information, see 
   :ref:`Using cURL<how-curl-commands-work>`.
   
To use this API, it helps to be familiar with HTTP/1.1, RESTful web services, the 
|service| service, and the JSON data serialization format.

.. _server-intro:

How Cloud Servers work
^^^^^^^^^^^^^^^^^^^^^^

Whether you choose to create a server by using the Cloud Control Panel, cURL, or the nova 
client, the basic steps are the same.

#. **Select a region for your Cloud Server**

   .. tip:: 

      To help you decide which regionalized endpoint to use, see 
      :kc-article:`special considerations<about-regions>`.

#. **Select your operating system**

   Choose from a variety of popular Linux® or Windows distributions. The operating system 
   for a server is known as its image.

#. **Select a flavor for your Cloud Server**

   Cloud Server flavors are a combination of RAM, disk space, disk I/O, vCPUs, and network 
   throughput. For more information on flavors, see :ref:`Flavors<flavors>`.

#. **Your server is online in just a few minutes**

   By using either the Cloud Control Panel or the API, you can upgrade or remove  your 
   Cloud Servers as your needs change. 
