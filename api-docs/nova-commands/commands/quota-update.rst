.. _nc-update-quota:

Update quota for a tenant
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Updates the quotas for a specified tenant.

**Usage:**

.. code::  

    $ nova quota-update [--instances <instances>] 
                    [--cores <cores>]
                    [--ram <ram>] 
                    [--volumes <volumes>]
                    [--gigabytes <gigabytes>]
                    [--floating-ips <floating_ips>]
                    [--metadata-items <metadata_items>]
                    [--injected-files <injected_files>]
                    [--injected-file-content-bytes <injected_file_content_bytes>]
                    <tenant_id>

**Positional argument:**

-  ``tenant_id``. The ID of the tenant for which you want to update quotas.

**Optional arguments:**

-  ``--instances`` ``instances``. New value for the ``instances`` quota.

-  ``--cores`` ``cores``. New value for the ``cores`` quota.

-  ``--ram`` ``ram``. New value for the ``ram`` quota.

-  ``--volumes`` ``volumes``. New value for the ``volumes`` quota.

-  ``--gigabytes`` ``gigabytes``. New value for the ``gigabytes`` quota.

-  ``--floating-ips`` ``floating-ips``. New value for the ``floating-ips`` quota.

-  ``--metadata-items`` ``metadata-items``. New value for the ``metadata-items`` quota.

-  ``--injected-files`` ``injected-files``. New value for the ``injected-files`` quota.

-  ``--injected-file-content-bytes`` ``injected-file-content-bytes``. New value for the 
   ``injected-file-content-bytes`` quota.

**Output:** None. If you run **nova quota-show**, you can see the updated quotas.
