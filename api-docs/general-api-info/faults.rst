.. _faults:

======
Faults
======

The API v2 handles the following types of faults:

-  Synchronous faults occur at request time.

-  Asynchronous faults occur in the background while a server or image
   is being built or a server is executing an action. When an
   asynchronous fault occurs, the system places the server or image in
   an ``ERROR`` state and embeds the fault in the offending server or
   image.

When a synchronous or asynchronous fault occurs, the fault contains an
HTTP status code, a human-readable message, and optional details about
the error. Additionally, an asynchronous fault might also contain a time
stamp that indicates when the fault occurred.

.. _faults-synchronous:

Synchronous Faults
~~~~~~~~~~~~~~~~~~

Synchronous faults occur at request time. When a synchronous fault
occurs, the fault contains an HTTP error response code, a human-readable
message, and optional details about the error.

**Example: Fault: JSON Response**

.. code::

    {
        "computeFault" : {
            "code" : 500,
            "message" : "Fault!",
            "details" : "Error Details..."
        }
    }


The error response code is returned in the body of the response for
convenience. The message section returns a human-readable message that
is appropriate for display to the end user. The details section is
optional and may contain information—for example, a stack trace—to
assist in tracking down an error. The detail section may or may not be
appropriate for display to an end user.

The root element of the fault, such as ``computeFault``, may change
depending on the type of error. The following table lists possible
elements with the associated error response codes:

**Fault Elements and Error Response Codes**

+---------------------------+-----------------------+-------------------------+
| Fault Element             | Associated Error      | Expected in All         |
|                           | Response Code         | Requests?               |
+===========================+=======================+=========================+
| computeFault              | 500, 400,             | Yes                     |
|                           | other codes possible  |                         |
+---------------------------+-----------------------+-------------------------+
| **Client errors**                                                           |
+---------------------------+-----------------------+-------------------------+
| badRequest                | 400                   | Yes                     |
+---------------------------+-----------------------+-------------------------+
| unauthorized              | 401                   | Yes                     |
+---------------------------+-----------------------+-------------------------+
| forbidden                 | 403                   | Yes                     |
+---------------------------+-----------------------+-------------------------+
| resizeNotAllowed          | 403                   |                         |
+---------------------------+-----------------------+-------------------------+
| itemNotFound              | 404                   |                         |
+---------------------------+-----------------------+-------------------------+
| Method Not Allowed        | 405                   |                         |
+---------------------------+-----------------------+-------------------------+
| buildInProgress           | 409                   |                         |
+---------------------------+-----------------------+-------------------------+
| backupOrResizeInProgress  | 409                   |                         |
+---------------------------+-----------------------+-------------------------+
| overLimit                 | 413                   | Yes                     |
+---------------------------+-----------------------+-------------------------+
| badMediaType              | 415                   |                         |
+---------------------------+-----------------------+-------------------------+
| **Server errors**                                                           |
+---------------------------+-----------------------+-------------------------+
| notImplemented            | 501                   |                         |
+---------------------------+-----------------------+-------------------------+
| serviceUnavailable        | 503                   | Yes                     |
+---------------------------+-----------------------+-------------------------+
| serverCapacityUnavailable | 503                   |                         |
+---------------------------+-----------------------+-------------------------+


**Example: Fault, Item Not Found: JSON Response**

.. code::

    {
        "itemNotFound" : {
            "code" : 404,
            "message" : "Not Found",
            "details" : "Error Details..."
        }
    }


From an XML schema perspective, all API faults are extensions of the
base fault type ``ComputeAPIFault``. When working with a system that binds
XML to actual classes (such as JAXB), you can use
``ComputeAPIFault`` as a “catch-all” if there's no interest in
distinguishing between individual fault types.

The ``OverLimit`` fault is generated when a rate limit threshold is
exceeded. For convenience, the fault adds a retryAt attribute that
contains the content of the Retry-After header in XML Schema 1.0
date/time format.

**Example: Fault, Over Limit: JSON Response**

.. code::

    {
        "overLimit" : {
            "code" : 413,
            "message" : "OverLimit Retry...",
            "details" : "Error Details...",
            "retryAt" : "2010-08-01T00:00:00Z"
        }
    }

.. _faults-asynchronous:

Asynchronous Faults
~~~~~~~~~~~~~~~~~~~

Asynchronous faults occur in the background while a server or image is
being built or a server is executing an action. When an asynchronous
fault occurs, the system places the server or image in an ``ERROR``
state and embeds the fault in the offending server or image.

When an asynchronous fault occurs, the fault contains an HTTP error
response code, a human readable message, and optional details about the
error. An asynchronous fault might also contain a time stamp that
indicates when the fault occurred.

**Example: Server in Error State: JSON**

.. code::

    {
        "server": {
            "id": "52415800-8b69-11e0-9b19-734f0000ffff",
            "tenant_id": "1234",
            "user_id": "5678",
            "name": "sample-server",
            "created": "2010-08-10T12:00:00Z",
            "hostId": "e4d909c290d0fb1ca068ffafff22cbd0",
            "status": "ERROR",
            "progress": 66,
            "image" : {
                "id": "52415800-8b69-11e0-9b19-734f6f007777"
            },
            "flavor" : {
                "id": "52415800-8b69-11e0-9b19-734f216543fd"
            },
            "fault" : {
                "code" : 404,
                "created": "2010-08-10T11:59:59Z",
                "message" : "Could not find image 52415800-8b69-11e0-9b19-734f6f007777",
                "details" : "Fault details"
            },
            "links": [
                {
                    "rel": "self",
                    "href": "http://dfw.servers.api.rackspacecloud.com/v2/010101/servers/52415800-8b69-11e0-9b19-734f000004d2"
                },
                {
                    "rel": "bookmark",
                    "href": "http://dfw.servers.api.rackspacecloud.com/010101/servers/52415800-8b69-11e0-9b19-734f000004d2"
                }
            ]
        }
    }


**Example: Image in Error State: JSON**

.. code::

    {
        "image" : {
            "id" : "52415800-8b69-11e0-9b19-734f5736d2a2",
            "name" : "My Server Backup",
            "created" : "2010-08-10T12:00:00Z",
            "status" : "SAVING",
            "progress" : 89,
            "server" : {
                "id": "52415800-8b69-11e0-9b19-734f335aa7b3"
            },
            "fault" : {
                "code" : 500,
                "message" : "An internal error occured",
                "details" : "Error details"
            },
            "links": [
                {
                    "rel" : "self",
                    "href" : "http://dfw.servers.api.rackspacecloud.com/v2/010101/images/52415800-8b69-11e0-9b19-734f5736d2a2"
                },
                {
                    "rel" : "bookmark",
                    "href" : "http://dfw.servers.api.rackspacecloud.com/010101/images/52415800-8b69-11e0-9b19-734f5736d2a2"
                }
            ]
        }
    }

.. _faults-badrequest:

badRequest
~~~~~~~~~~

The ``badRequest`` fault indicates that the data in the request object is
invalid. For example, a string was used in a parameter that accepts only an
integer. The fault wraps validation errors.

**Example: badRequest fault response**

.. code::

    <badRequest xmlns="http://docs.openstack.org/loadbalancers/api/v1.0" code="400">
        <message>Validation fault</message>
        <details>The object is not valid</details>
            <validationErrors>
                <message>Server ip is invalid. Please specify a valid ip.</message>
            </validationErrors>
    </badRequest>

.. _faults-itemnotfound:

itemNotFound
~~~~~~~~~~~~

The ``itemNotFound`` fault is returned when a requested resource is not found.

**Example: itemNotFound fault response**

.. code::

    <itemNotFound code="404" xmlns="http://docs.openstack.org/loadbalancers/api/v1.0">
        <message>Object not Found</message>
    </itemNotFound>

overLimit
~~~~~~~~~

The ``overLimit`` fault is returned when you exceed a currently allocated limit.

**Example: overLimit fault response**

.. code::

    <overLimit code="413" xmlns="http://docs.openstack.org/loadbalancers/api/v1.0">
        <message>Your account is currently over the limit so your request could not be processed.</message>
    </overLimit>

.. _faults-serviceunavailable:

serviceUnavailable
~~~~~~~~~~~~~~~~~~

The ``serviceUnavailable`` fault is returned when the service is unavailable,
such as when the service is undergoing maintenance. This fault does not
necessarily  mean that the currently configured load balancers are unable to
process traffic;  it simply means that the API is currently unable to service
requests.

**Example: serviceUnavailable fault response**

.. code::

    <serviceUnavailable code="500" xmlns="http://docs.openstack.org/loadbalancers/api/v1.0">
        <message>The Load balancing service is currently not available</message>
    </serviceUnavailable>

.. _faults-unauthorized:

unauthorized
~~~~~~~~~~~~

The ``unauthorized`` fault is returned when you are not authorized to perform
an attempted operation.

**Example: unauthorized fault response**

.. code::

    <unauthorized code="404" xmlns="http://docs.openstack.org/loadbalancers/api/v1.0">
        <message>You are not authorized to execute this operation.</message>
    </unauthorized>




