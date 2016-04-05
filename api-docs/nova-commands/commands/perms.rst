==================================================================================================================
Step 1. Get Admin API Permissions - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
==================================================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  Step 1. Get Admin API Permissions
   :name: step-1.-get-admin-api-permissions
   :class: title

To run nova or supernova client commands including the reset state and
services extensions, you must request to be added to an LDAP group with
the correct permissions.

 
**To get admin API permissions**

1. Log into
   `RackerApp <https://rackerapp.rackspace.com:8443/IDMProv/portal/cn/GuestContainerPage/Welcome>`__.

2. On the left side of the  , click **Make a Process Request**.

3. In the **Process Request Category**, select **Groups**. Then, click
   **Continue**.

4. Click **Group Access Request**.

5. Scroll to and select one of the following groups:

   -  ``lnx-CloudServers-SupportL1``

   -  ``lnx-CloudServers-SupportL2``

   -  ``lnx-CloudServers-SupportL3``

6. Enter a reason for your request and click **Submit**.
