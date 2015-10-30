==============
About the API
==============

Next generation Cloud Servers :rax:`powered by OpenStack <cloud/openstack/>` is a fast,
reliable, and scalable cloud compute solution without the risk of
proprietary lock-in. It provides the core features of the OpenStack
Compute *API* |contract version| and also deploys certain extensions as permitted by the
OpenStack Compute API contract. Some of these extensions are generally
available through OpenStack while others implement Rackspace-specific
features to meet customers’ expectations and for operational
compatibility. The OpenStack Compute API and the Rackspace extensions
are known collectively as API |contract version|.

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

   For more information about the server migration see the article: 
   :kc-article:`First Generation to Next Generation cloud server migration <first-generation-to-next-generation-cloud-server-migration-faq>`

This document describes the features available with API |contract version|.


.. toctree:: :hidden:
   :maxdepth: 3
   
   additional-resources
   pricing-and-service-level
   api-software-updates
