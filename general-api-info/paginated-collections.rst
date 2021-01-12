.. _paginated-collections:

=====================
Paginated collections
=====================

To reduce load on the service, list operations return a maximum number
of items at a time. The maximum number of items returned is
1000.

To reduce load on the service, retrieve operations return a maximum limit of
100 items at a time. If a request supplies no limit or one that exceeds the
configured  default limit, the default limit is used instead.

This behavior is called *pagination*. Pagination gives you the ability to limit
the  size of the returned data and to retrieve a specified subset of a large
data set.  Pagination has two key concepts: limit and marker.

* *Limit* is the restriction on the maximum number of items for that type that
  can be returned.

* *Marker* is a reference to an object's ID and is in the list of paged results
  for a particular resource. For example, if the resource is a load balancer,
  the marker is the load balancer ID at which to begin the list of the paged
  results.

To navigate the collection, you can set the ``limit`` and ``marker`` parameters
in the URI. For example, ``?limit=10&marker=1234`` displays a maximum of 10
load balancers in the paginated results, beginning with the load balancer whose
ID is 1234.

You can also use the ``offset`` parameter, which is a count of the number
of objects from where the paginated list is started.

If a marker beyond the end of a list is given, an empty list is returned.

For convenience, collections contain atom ``next`` links and can
optionally contain ``previous`` links. The last page in the collection
will not contain a ``next`` link.

The following examples show pages in a collection of images.

To get the first page, issue a **GET** request to the following endpoint
and set the ``limit`` parameter to the page size of a single item::

    http://dfw.servers.api.rackspacecloud.com/v2/010101/images?limit=1

Subsequent links honor the initial page size. A client can follow links
to traverse a paginated collection.

JSON Collection
~~~~~~~~~~~~~~~

In JSON, members in a paginated collection are stored in a JSON array
named after the collection. A JSON object can also hold members in cases
where using an associative array is more practical. Properties about the
collection itself, including links, are contained in an array with the
name of the entity an underscore (\_) and ``links``. The combination of
the objects and arrays that start with the name of the collection and an
underscore represent the collection in JSON.

This approach allows for extensibility of paginated collections by
allowing them to be associated with arbitrary properties. It also allows
collections to be embedded in other objects.

**Example: Images Collection – First Page: JSON**

.. code::

    {
        "images": [
            {
                "id": "52415800-8b69-11e0-9b19-734f6f006e54",
                "name": "CentOS 5.2",
                "links": [
                    {
                        "rel": "self",
                        "href": "http://dfw.servers.api.rackspacecloud.com/v2/010101/images/52415800-8b69-11e0-9b19-734f6f006e54"
                    }
                ]
            }
        ],
        "images_links" : [
            {
                "rel": "next",
                "href": "http://dfw.servers.api.rackspacecloud.com/v2/010101/images?limit=1&marker=52415800-8b69-11e0-9b19-734f6f006e54"
            }
        ]
    }


**Example: Images Collection – Second Page: JSON**

.. code::

    {
        "images" :  [
                {
                    "id" : "52415800-8b69-11e0-9b19-734f5736d2a2",
                    "name" : "My Server Backup",
                    "links": [
                        {
                            "rel" : "self",
                            "href" : "http://dfw.servers.api.rackspacecloud.com/v2/010101/images/52415800-8b69-11e0-9b19-734f5736d2a2"
                        }
                    ]
                }
            ],
        "images_links": [
            {
                "rel" : "next",
                "href" : "http://dfw.servers.api.rackspacecloud.com/v2/010101/images?limit=1&marker=52415800-8b69-11e0-9b19-734f5736d2a2"
            }
        ]
    }

|

**Example: Images Collection – Last Page: JSON**

.. code::

    {
        "images": [
            {
                "id": "52415800-8b69-11e0-9b19-734f6ff7c475",
                "name": "Backup 2",
                "links": [
                    {
                        "rel": "self",
                        "href": "http://dfw.servers.api.rackspacecloud.com/v2/010101/images/52415800-8b69-11e0-9b19-734f6ff7c475"
                    }
                ]
            }
        ]
    }

