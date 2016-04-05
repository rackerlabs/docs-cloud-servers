.. _server-actions-extension:

Services Extension
~~~~~~~~~~~~~~~~~~~~~~~

The services extension allows you to get information about currently running services. For 
example, as a nova administrator, you might need information about the currently running 
services so that you can start, stop, or suspend those services.

You can use this extension through the API directly or through an extension to the nova 
client. To use this extension through the nova client, you must install the novaclient 
package with the services extension. 

Services operations
^^^^^^^^^^^^^^^^^^^^^^^

For examples of these operations, see the following operations:

- :ref:`List services <get-services>`
- :ref:`List servers for a service <get-services-servers>`
- :ref:`Show service version <get-service-version>`
- :ref:`Show basic service information <get-service-info>`
- :ref:`Show service details <get-service-details>`
- :ref:`Enable service<post-enable-service>`
- :ref:`Disable service<post-disable-service>`
- :ref:`Show service configuration <get-service-configuration>`
