.. _nc-get-credentials:

Get credentials
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Performs authentication.

**Usage:**

.. code::  

   $ nova credentials

Successful authentication returns user credentials, including ID, name, roles, and the 
authentication token. The token appears in the ``id`` field in the ``Token`` box.

.. code::  

   +------------------+---------------------------------------------------------------------------------------+
   | User Credentials | Value                                                                                 |
   +------------------+---------------------------------------------------------------------------------------+
   | id               | 170454                                                                                |
   | name             | MyRackspaceAcct                                                                       |
   | roles            | [{u'description': u'User Admin Role.', u'id': u'3', u'name': u'identity:user-admin'}] |
   +------------------+---------------------------------------------------------------------------------------+
   +---------+----------------------------------------+
   | Token   | Value                                  |
   +---------+----------------------------------------+
   | expires | 2012-07-28T13:58:56.000-05:00          |
   | id      | 1bd336d5-e0c6-49d9-b902-d3dbdc463062   |
   | tenant  | {u'id': u'010101', u'name': u'010101'} |
   +---------+----------------------------------------+

After you generate a token, the nova client automatically injects the token into any nova 
client commands that you issue. However, because the token expires after 24 hours, you must 
generate a new token once a day. 
