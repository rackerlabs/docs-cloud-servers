
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _post-get-console-servers-server-id-action:

Get console
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /servers/{server_id}/action

This operation returns a URL which you use with a java client to open a console connection 
to your server.

In the URI, specify the server ID.

To use the URL returned from this operation, you should download and install a VNC Viewer 
like `Real VNC <https://www.realvnc.com/products/vnc/documentation/4.0/win/java.html>`__ 
or `Tight VNC <http://www.tightvnc.com/download.php>`__. Then, from the directory where 
you saved the Vnc Viewer, run the following command (using the installed jar and the URL 
from the operation response body):

.. code::

   java -jar VncViewer.jar URL {returnedURL}

This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200 203                   |Success                  |Request succeeded.       |
+--------------------------+-------------------------+-------------------------+
|400                       |Error                    |A general error has      |
|                          |                         |occured.                 |
+--------------------------+-------------------------+-------------------------+
|401                       |Unauthorized             |Unauthorized.            |
+--------------------------+-------------------------+-------------------------+
|403                       |Forbidden                |Forbidden.               |
+--------------------------+-------------------------+-------------------------+
|405                       |Bad Method               |Bad method.              |
+--------------------------+-------------------------+-------------------------+
|409                       |Conflicting Reqest       |Conflicting request.     |
+--------------------------+-------------------------+-------------------------+
|413                       |Over Limit               |The number of items      |
|                          |                         |returned is above the    |
|                          |                         |allowed limit.           |
+--------------------------+-------------------------+-------------------------+
|500                       |API Fault                |API fault.               |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The requested service is |
|                          |                         |unavailable.             |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{server_id}               |Uuid                     |The UUID for the server. |
+--------------------------+-------------------------+-------------------------+





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|parameters.\ **os-        |Object *(Required)*      |A container for console  |
|getVNCConsole**           |                         |request.                 |
+--------------------------+-------------------------+-------------------------+
|parameters.os-            |String *(Required)*      |A key pair with the type |
|getVNCConsole.\ **type**  |                         |of vnc console,          |
|                          |                         |containing the value     |
|                          |                         |``"xvpvnc"``.            |
+--------------------------+-------------------------+-------------------------+





**Example Get console: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "os-getVNCConsole": 
           {
               "type": "xvpvnc"
           }
   }





Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|parameters.\ **console**  |Object                   |A container for console  |
|                          |                         |response.                |
+--------------------------+-------------------------+-------------------------+
|parameters.console.\      |String                   |The URL for the console  |
|**url**                   |                         |for the specified        |
|                          |                         |server. Open this URL in |
|                          |                         |a browser to open a VNC  |
|                          |                         |console to the server.   |
+--------------------------+-------------------------+-------------------------+
|parameters.console.\      |String                   |The type of VNC console  |
|**type**                  |                         |to the server, for       |
|                          |                         |example ``"xvpvnc"``.    |
+--------------------------+-------------------------+-------------------------+







**Example Get console: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 143
       Content-Type: application/json
       Date: Tue, 30 Jun 2015 17:38:17 GMT, Tue, 30 Jun 2015 17:38:19 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-910673e3-3b1c-45ce-9f87-6c2eea304692


.. code::

   {
     "console": {
       "url": "https://dfw.servers.console.rackspacecloud.com:443/console?token=b40c6057-4bcb-4ee7-a359-dcecc752b379",
       "type": "xvpvnc"
     }
   }




