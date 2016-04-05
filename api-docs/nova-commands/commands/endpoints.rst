.. _nc-get-endpoints:

Get a list of endpoints
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Discovers service endpoints for which the user has been authenticated.

**Usage:**

.. code::  

    $ nova endpoints

**Output:**

.. code::  

    +-----------------+-------------------------------------------+
    | ordprodadminapi | Value                                     |
    +-----------------+-------------------------------------------+
    | adminURL        | https://10.23.244.90:8774/v2/nova-staging |
    | publicURL       | https://10.23.244.90:8774/v2/nova-staging |
    | region          | ordprodadmin                              |
    | serviceName     | ordprodadminapi                           |
    +-----------------+-------------------------------------------+

For each service, the response includes the admin URL, public URL, region, and service name.

