.. _limits:

======
Limits
======

All accounts, by default, have a preconfigured set of thresholds, or *limits*,
to manage capacity and prevent abuse of the system. The system recognizes two
kinds of limits: *rate limits* and *absolute limits*. Rate limits are
thresholds that are reset after a certain amount of time passes. Absolute
limits are fixed. Rate limits are processed via the `Repose service`_.

.. note::

    If the default limits are too low for your particular application,
    contact Rackspace Cloud support to request an increase. All requests
    require reasonable justification.

.. _Repose service: http://www.openrepose.org

The system recognizes the following types of limits:

-  *rate limits*. Control the frequency at which the user can issue
   specific API requests. See :ref:`rate-limits`.

-  *absolute limits*. Control the total number of specific objects that
   the user can possess simultaneously. See :ref:`absolute-limits`.

To query the limits programmatically, see
:ref:`Retrieve list of rate and absolute limits
<get-retrieve-list-of-rate-and-absolute-limits-limits>`.

.. _rate-limits:

Rate Limits
~~~~~~~~~~~

Rate limits control the frequency at which the user can issue specific
API requests.

Rate limits are reset after a certain amount of time passes. To request
a rate limit increase, contact Rackspace.

Rate limits are specified in terms of both a human-readable wildcard URI and a
machine-processable regular expression. The regular expression boundary matcher
``^`` for the rate limit takes effect after the root URI path. For example, the
regular expression ``^/servers`` would match the resources portion of the
following URI::

    https://dfw.servers.api.rackspacecloud.com/v2/010101/servers

The following table lists the default rate limits:

.. list-table:: **Default rate limits**
   :widths: 20 40 30
   :header-rows: 1

   * - Method
     - URI
     - Default Limit
   * - GET
     - ``*``
     - 1000 per minute
   * - GET
     - ``/servers/{id}/os-virtual-interfacesv2``
     - 25 per minute
   * - POST
     - ``*``
     - 100 per minute
   * - POST
     - ``/os-networksv2``
     - 100 per day
   * - POST
     - ``/servers *``
     - 1000 per day
   * - POST
     - ``/servers/{id}/os-virtual-interfacesv2``
     - 4 per minute

Rate limits are applied in order relative to the method, going from least to
most specific.  If you exceed the limits established for your account, a
``413 (Rate Control)`` HTTP  response is returned with a ``Retry-After`` header
to notify the client when it can  attempt to try again.

To find your current account settings for these limits, see
:ref:`Retrieve list of limits including used
limits <get-retrieve-list-of-limits-including-used-limits-limits>`.

.. _absolute-limits:

Absolute Limits
~~~~~~~~~~~~~~~

Absolute limits control the total number of specific objects that the
user can possess simultaneously.

Specify absolute limits to limit the overall number of items or amount
of capacity in the system. Absolute limits also include the amount of
resources currently consumed, which allow for programmatic visibility of
usage.

Specify absolute limits as name/value pairs.

The following ``Default`` limits show the maximum amount of a resource that
can be used:

.. list-table:: **Absolute limits**
   :widths: 20 40 10
   :header-rows: 1

   * - Name
     - Description
     - Default
   * - maxImageMeta
     - The maximum number of metadata key value pairs associated with a
       particular image
     - 40
   * - maxPersonality
     - The maximum number of file path/content pairs that can be supplied on
       server build and rebuild
     - 5
   * - maxPersonalitySize
     - The maximum size, in bytes, for each personality file
     - 1000
   * - maxServerMeta
     - The maximum number of metadata key value pairs associated with a
       particular server
     - 40
   * - maxTotalCores
     - This limit is disabled, so no limits exist on the total number of cores
     - -1
   * - maxTotalInstances
     - The maximum number of Cloud Servers at any one time
     - 100
   * - maxTotalPrivateNetworks
     - The maximum number of isolated networks that you can create. Set to 0
       when Cloud Networks is disabled, 10 when Cloud Networks enabled
     - 10
   * - maxTotalRAMSize
     - The maximum total amount of RAM (MB) of all Cloud Servers at any time
     - 131072


The following ``total`` limits show current usage:

+ **totalCoresUsed**: The total number of cores used.

+ **totalInstancesUsed**: The total number of Cloud Servers.

+ **totalRAMUsed**: The total amount of RAM (GB) used for all Cloud Servers.
