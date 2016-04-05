=============================================================================================
Authenticate - Next Generation Cloud Servers™ Administrator Guide  - OpenStack Compute API v2
=============================================================================================

INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL
-  INTERNAL - RAX INTERNAL -  INTERNAL - RAX INTERNAL -  INTERNAL - RAX
INTERNAL - 

.. rubric::  Authenticate
   :name: authenticate
   :class: title

Shows user credentials returned from authentication endpoint.

**Usage:**

.. code::  

    $ nova credentials

**Output:**

.. code::  

    +------------------+----------------------------------------------------------------------------------------------------------------------------------------+
    | User Credentials | Value                                                                                                                                  |
    +------------------+----------------------------------------------------------------------------------------------------------------------------------------+
    | id               | dian4554                                                                                                                               |
    | name             | dian4554                                                                                                                               |
    | roles            | [{u'id': 1, u'name': u'support_L2'}, {u'id': 2, u'name': u'admin'}, {u'id': 3, u'name': u'admin'}, {u'id': 4, u'name': u'user-admin'}] |
    | roles_links      | []                                                                                                                                     |
    | username         | dian4554                                                                                                                               |
    +------------------+----------------------------------------------------------------------------------------------------------------------------------------+
    +---------+----------------------------------------------------------------------+
    | Token   | Value                                                                |
    +---------+----------------------------------------------------------------------+
    | expires | 2012-09-01T16:51:28Z                                                 |
    | id      | bfb9c7badf664712aa8fa86462907180                                     |
    | tenant  | {u'enabled': True, u'id': u'nova-staging', u'name': u'nova-staging'} |
    +---------+----------------------------------------------------------------------+

Successful authentication returns user credentials, including ID, name,
roles, and the authentication token. The token appears in the ``id``
field in the ``Token`` box.

After you generate a token, the nova client automatically sources the
token into any nova client commands that you issue.

However, because the token expires after 24 hours, you must generate a
new token once a day.

**Corresponding API call:** `Authentication through the Rackspace Cloud
Identity
Service <http://docs.rackspace.com/servers/api/v2/cs-devguide/content/auth.html>`__.
