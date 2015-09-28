==============
About the API
==============

Next generation Cloud Servers `powered by
OpenStack <http://www.rackspace.com/cloud/openstack/>`__ is a fast,
reliable, and scalable cloud compute solution without the risk of
proprietary lock-in. It provides the core features of the OpenStack
Compute *API* v2 and also deploys certain extensions as permitted by the
OpenStack Compute API contract. Some of these extensions are generally
available through OpenStack while others implement Rackspace-specific
features to meet customers’ expectations and for operational
compatibility. The OpenStack Compute API and the Rackspace extensions
are known collectively as API v2.

.. important:: During 2015, all First Generation servers will be migrated to
   Next Generation servers, on a rolling basis.

   Notification from Rackspace will be sent to customers informing them of
   their 30-day window to complete the migration of the specified servers.
   If you take no action, your server will be migrated for you.

   To migrate your servers, during your migration window, simply perform a
   ``SOFT`` reboot on your first gen server, either from the Control Panel
   or by using the reboot API operation. The migration process will
   preserve all data and configuration settings.

   During the 30-day migration window, performing a ``HARD`` reboot on a
   first gen server will reboot the server without triggering the
   migration.

   You can see information about your migration window's open and close
   dates, use the Get Server Details on your first gen server, and look in
   the metadata section of the response for
   "FG2NG\_self\_migration\_available\_till" and
   "FG2NG\_self\_migration\_available\_from" key pairs. If your migration
   window has not been scheduled, you will not see these metadata keys.

   For more information about the server migration see the Knowledge Center
   article: `First Generation to Next Generation cloud server migration
   FAQ <http://www.rackspace.com/knowledge_center/article/first-generation-to-next-generation-cloud-server-migration-faq>`__

This document describes the features available with API v2.

We welcome feedback, comments, and bug reports. Log into the Rackspace
customer portal at https://feedback.rackspace.com/.

Pricing and terms of service
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cloud Servers is part of the Rackspace Cloud. The cost for API usage follows the `pricing 
schedule for the service`_.

The service level agreement (SLA) for Rackspace Cloud Services is included in the `Rackspace Cloud SLA`_.

The terms of service are part of the `Rackspace Cloud Terms of Service`_. Periodically 
review these terms because they can be updated any time.

.. _pricing schedule for the service: http://www.rackspace.com/cloud/public/servers/pricing
.. _Rackspace Cloud SLA: http://www.rackspace.com/information/legal/cloud/sla
.. _Rackspace Cloud Terms of Service: http://www.rackspace.com/information/legal/cloud/tos

Additional resources
~~~~~~~~~~~~~~~~~~~~

We welcome feedback, comments, and bug reports. Visit the Rackspace customer portal 
at https://feedback.rackspace.com/.

Use the links below to learn more about the Rackspace Cloud Servers service and API.

- For general information about Cloud Servers, see the `Cloud Servers FAQ`_ 
  in the Rackspace Knowledge Center.

- To learn more about the Cloud Servers service and the various ways you can interact 
  with it (API, SDK, CLI, and Control Panel), see the `Rackspace Cloud Guide to Core Infrastructure Services`_.
  
- To learn about using Rackspace Cloud SDKs, see `Software Development Kits & Tools`_. 
    
- To get information about other Rackspace Cloud services APIs, see the
  `Rackspace API Documentation`_.


.. _Rackspace Cloud Guide to Core Infrastructure Services: https://developer.rackspace.com/docs/user-guides/infrastructure/
.. _Cloud Servers FAQ: http://www.rackspace.com/knowledge_center/product-faq/cloud-servers
.. _Rackspace API Documentation: https://developer.rackspace.com/docs/
.. _Software Development Kits & Tools: https://developer.rackspace.com/docs/#sdks