.. _post-import-a-server-key-pair-os-keypairs:

Import a server key pair
------------------------

.. code::

    POST /os-keypairs

This operation imports, or uploads, a key pair, with the name and public key
specified in the request body, to associate with a new server instance.


This table shows the possible response codes for this operation:

+-------------------------+-------------------------+-------------------------+
|Response Code            |Name                     |Description              |
+=========================+=========================+=========================+
|200                      |Success                  |Request accepted.        |
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

This table shows the body parameters for the request:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**keypair**               |Object                  |The container for the    |
|                          |                        |key pair request.        |
+--------------------------+------------------------+-------------------------+
|keypair.\ **name**        |String                  |The name to associate    |
|                          |                        |with the key pair.       |
+--------------------------+------------------------+-------------------------+
|keypair.\ **public_key**  |String                  |The public ssh key value.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+

**Example Import a server key pair: JSON request**

.. code::

   X-Auth-Token: f064c46a782c444cb4ba4b6434288f7c
   Content-Type: application/json
   Accept: application/json


.. code::

   {
       "keypair":{
           "name":"name_of_keypair",
           "public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQDx8nkQv/zgGgB4rMYmIf+6A4l6Rr+o/6lHBQdW5aYd44bd8JttDCE/F/pNRr0lRE+PiqSPO8nDPHw0010JeMH9gYgnnFlyY3/OcJ02RhIPyyxYpv9FhY+2YiUkpwFOcLImyrxEsYXpD/0d3ac30bNH6Sw9JD9UZHYcpSxsIbECHw"
       }
   }


Response
^^^^^^^^

This table shows the body parameters for the response:

+--------------------------+------------------------+-------------------------+
|Name                      |Type                    |Description              |
+==========================+========================+=========================+
|**keypair**               |Object                  |The container for the    |
|                          |                        |key pair details.        |
+--------------------------+------------------------+-------------------------+
|keypair.\ **fingerprint** |String                  |A short sequence of      |
|                          |                        |bytes used to            |
|                          |                        |authenticate, or look    |
|                          |                        |up, a longer public key. |
+--------------------------+------------------------+-------------------------+
|keypair.\ **name**        |String                  |The name of the key pair.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|keypair.\ **private_key** |String                  |The private ssh key      |
|                          |                        |value.                   |
+--------------------------+------------------------+-------------------------+
|keypair.\ **public_key**  |String                  |The public ssh key value.|
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+
|keypair.\   **user_id**   |String                  |The ID of the user.      |
|                          |                        |                         |
+--------------------------+------------------------+-------------------------+


**Example Import a server key pair: JSON response**


.. code::

       Status Code: 200 OK
       Content-Length: 545
       Content-Type: application/json
       Date: Thu, 02 Apr 2015 18:08:19 GMT, Thu, 02 Apr 2015 18:08:19 GMT
       Server: Jetty(9.2.z-SNAPSHOT)
       Via: 1.1 Repose (Repose/6.2.1.2)
       X-Compute-Request-Id: req-9efa9191-4f08-4d65-92c7-acd934e5c5b0


.. code::

   {
       "keypair":{
           "fingerprint":"1e:2c:9b:56:79:4b:45:77:f9:ca:7a:98:2c:b0:d5:3c",
           "name":"name_of_keypair-dab428fe-6186-4a14-b3de-92131f76cd39",
           "public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQDx8nkQv/zgGgB4rMYmIf+6A4l6Rr+o/6lHBQdW5aYd44bd8JttDCE/F/pNRr0lRE+PiqSPO8nDPHw0010JeMH9gYgnnFlyY3/OcJ02RhIPyyxYpv9FhY+2YiUkpwFOcLImyrxEsYXpD/0d3ac30bNH6Sw9JD9UZHYcpSxsIbECHw== Generated by Nova",
           "user_id":"fake"
       }
   }




