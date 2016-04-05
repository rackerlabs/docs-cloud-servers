.. _getting-started-guide:

Getting Started Guide
-----------------------

Use this *Getting Started Guide* to learn how to authenticate, send API requests, 
and complete basic operations by using the |apiservice|.

For more information about Cloud Servers concepts and API operations, see the 
:ref:`Developer Guide<developer-guide>` and the :ref:`API Reference<api-reference>`. 
   
To use this API, it helps to be familiar with HTTP/1.1, RESTful web services, the 
|service| service, and the JSON data serialization format.

Rackspace support personnel must perform administrative tasks and complete actions on 
specific services for customers. For example, you may need to place a compute node on a 
host with a failing disk into maintenance mode. In maintenance mode, no one is permitted 
to create new instances, and you can move active instances off the host.

To perform administrative tasks, you can use nova client commands, so this guide includes 
many of the available nova commands.  For a complete list of commands, use the 
``nova help`` command.

To reset the state of a server instance, use the reset state extension. You might need to 
reset the state of an instance to ``ERROR`` state so that you can delete it.

To get information about and manage currently running services, use the services extension. 
For example, you may need information about the currently running services so that you can 
start, stop, or suspend those services.


.. toctree::
   :maxdepth: 1

   Prerequisites <prerequisites-for-using-api>
   Send API requests <send-request-ovw>
   Authenticate <authenticate>