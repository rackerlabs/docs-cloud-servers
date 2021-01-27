.. _post-get-console-servers-server-id-action:

Get console
-----------

.. code::

    POST /servers/{server_id}/action

This operation returns a URL which you use with either a java client or an
HTML-based novnc console to open a console connection to your server.

In the URI, specify the server ID.

To use the URL returned from this operation with the java option, you should
download and install a VNC Viewer like
`Real VNC <https://www.realvnc.com/products/vnc/documentation/4.0/win/java.html>`__
or `Tight VNC <http://www.tightvnc.com/download.php>`__. Then, from the
directory where you saved the Vnc Viewer, run the following command (using the
installed jar and the URL from the operation response body):

.. code::

   java -jar VncViewer.jar URL {returnedURL}

To use the URL returned from this operation with the HTML novnc option, open a
browser and copy the URL to the address bar of the browser.

The following table shows the possible response codes for this operation:

+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200 203                  |Success                  |Request succeeded.       |
+-------------------------+-------------------------+-------------------------+
|400                      |Error                    |A general error has      |
|                         |                         |occured.                 |
+-------------------------+-------------------------+-------------------------+
|401                      |Unauthorized             |Unauthorized.            |
+-------------------------+-------------------------+-------------------------+
|403                      |Forbidden                |Forbidden.               |
+-------------------------+-------------------------+-------------------------+
|405                      |Bad Method               |Bad method.              |
+-------------------------+-------------------------+-------------------------+
|409                      |Conflicting Reqest       |Conflicting request.     |
+-------------------------+-------------------------+-------------------------+
|413                      |Over Limit               |The number of items      |
|                         |                         |returned is above the    |
|                         |                         |allowed limit.           |
+-------------------------+-------------------------+-------------------------+
|500                      |API Fault                |API fault.               |
+-------------------------+-------------------------+-------------------------+
|503                      |Service Unavailable      |The requested service is |
|                         |                         |unavailable.             |
+-------------------------+-------------------------+-------------------------+


Request
^^^^^^^

The following table shows the URI parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|{server_id}               |Uuid                    |The UUID for the server. |
+--------------------------+------------------------+-------------------------+

The following table shows the body parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**os- getVNCConsole**     |Object                  |A container for console  |
|                          |                        |request.                 |
+--------------------------+------------------------+-------------------------+
|os- getVNCConsole.\       |String                  |A key pair with the type |
|**type**                  |                        |of vnc console,          |
|                          |                        |containing the value     |
|                          |                        |``"xvpvnc"`` or          |
|                          |                        |``"novnc"``.             |
+--------------------------+------------------------+-------------------------+

**Example Get console - java: JSON request**


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

**Example Get console - novnc: JSON request**


.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "os-getVNCConsole":
           {
               "type": "novnc"
           }
   }

Response
^^^^^^^^

The following table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**console**               |Object                  |A container for console  |
|                          |                        |response.                |
+--------------------------+------------------------+-------------------------+
|console.\   **url**       |String                  |The URL for the console  |
|                          |                        |for the specified        |
|                          |                        |server. Open this URL in |
|                          |                        |a browser to open a VNC  |
|                          |                        |console to the server.   |
+--------------------------+------------------------+-------------------------+
|console.\ **type**        |String                  |The type of VNC console  |
|                          |                        |to the server, for       |
|                          |                        |example ``"xvpvnc"``.    |
+--------------------------+------------------------+-------------------------+

**Example Get console - java: JSON response**


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

**Example Get console - novnc: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 143
       Content-Type: application/json
       Date: Tue, 30 Jun 2015 17:345:17 GMT, Tue, 30 Jun 2015 17:45:19 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-9235673f2-4a1d-75cc-2a22-5d3fef994122


.. code::

   {
     "console": {
       "url": "https://dfw.servers.console.rackspacecloud.com:443/console?token=a71d5697-2aca-5ea2-d991-abad292b351",
       "type": "novnc"
     }
   }


