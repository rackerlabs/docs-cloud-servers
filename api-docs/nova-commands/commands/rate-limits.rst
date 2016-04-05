.. _nc-get-rate-limits:

Get rate limits 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lists rate limits for a user.

**Usage:**

.. code::  

    $ nova rate-limits

**Output:**

.. code::  

    +--------+-----------------+-------+--------+--------+----------------------+
    | Verb   | URI             | Value | Remain | Unit   | Next_Available       |
    +--------+-----------------+-------+--------+--------+----------------------+
    | DELETE | *               | 100   | 100    | MINUTE | 2012-08-31T16:55:01Z |
    | GET    | *changes-since* | 3     | 3      | MINUTE | 2012-08-31T16:55:01Z |
    | POST   | *               | 10    | 10     | MINUTE | 2012-08-31T16:55:01Z |
    | POST   | */servers       | 50    | 50     | DAY    | 2012-08-31T16:55:01Z |
    | PUT    | *               | 10    | 10     | MINUTE | 2012-08-31T16:55:01Z |
    +--------+-----------------+-------+--------+--------+----------------------+

The response includes the following information:

+----------------+-----------------------------------------------------------+
| Field          | Description                                               |
+================+===========================================================+
| Verb           | The name of the verb.                                     |
+----------------+-----------------------------------------------------------+
| URI            | The name of the URI resource.                             |
+----------------+-----------------------------------------------------------+
| Value          | The limit value.                                          |
+----------------+-----------------------------------------------------------+
| Remain         | The amount of unused resources.                           |
+----------------+-----------------------------------------------------------+
| Unit           | The unit for the resource.                                |
+----------------+-----------------------------------------------------------+
| Next_Available | The date and timestamp when the resource will be next     |
|                | available.                                                |
+----------------+-----------------------------------------------------------+

**Corresponding API call:** **Corresponding API call:** 
:rax-devdocs:`Retrieve list of rate and absolute limits<cloud-servers/v2/developer-guide/#retrieve-list-of-rate-and-absolute-limits>`

