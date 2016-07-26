.. _role-based-access-control:

================================
Role-based access control (RBAC)
================================

Role Based Access Control (RBAC) restricts access to the capabilities of
Rackspace Cloud services, including the Cloud Servers API, to authorized users
only. RBAC enables Rackspace Cloud customers to specify which account users of
their Cloud account have access to which |product name| API service
capabilities, based on roles defined by Rackspace (see
:ref:`Roles Available for Cloud Servers <rbac-available-roles>`). The permissions to
perform certain operations in |product name| API (create, read, update, delete)
are assigned to specific roles. The account owner user assigns these roles,
either global (multiproduct) or product-specific (for example, |product name|),
to account users.

.. _rbac-assign:

Assigning Roles to Account Users
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The account owner (identity:user-admin) can create account users on the account
and then assign roles to those users. The roles grant the account users
specific permissions for accessing the capabilities of the |product name|
service. Each account has only one account owner, and that role is assigned by
default to any Rackspace Cloud account when the account is created.

See the Cloud Identity API guide for information about how to perform the
following tasks:

* :rax-devdocs:`Add account users <cloud-identity/v2/developer-guide/#add-user>`

* :rax-devdocs:`Add role to user \
  <cloud-identity/v2/developer-guide/#add-role-to-user>`

* :rax-devdocs:`Delete global role from user \
  <cloud-identity/v2/developer-guide/#delete-global-role-from-user>`

.. note::

    The account owner (identity:user-admin) role cannot hold any additional
    roles because it already has full access to all capabilities.

.. _rbac-available-roles:

Roles Available for Cloud Servers
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following table describes the roles that can be used to access the
|product name| API.

.. list-table:: **Product roles and capabilities**
   :widths: 20 50
   :header-rows: 1

   * - Role name
     - Role permissions
   * - nova:admin
     - This role provides Create, Read, Update, and Delete permissions
       in |product name|, where access is granted.
   * - lbaas:creator
     - This role provides Create, Read and Update permissions in
       |product name|, where access is granted.
   * - lbaas:observer
     - This role provides Read permission in |product name|, where access is
       granted.

.. _rbac-available-multi-roles:

Multiproduct global roles and permissions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Additionally, two multiproduct roles apply to all products. Users with
multiproduct roles inherit access to future products when those products become
RBAC-enabled. The following list describes these roles and their permissions.

**Multiproduct (Global) Roles and Permissions**

.. list-table:: **Multiproduct roles and permissions**
   :widths: 20 40
   :header-rows: 1

   * - Role name
     - Role permissions
   * - admin
     - This role provides create, read, update, and delete permissions
       in all products, where access is granted.
   * - observer
     - This role provides read permission in all products,
       where access is granted.

.. _rbac-resolve-role-conflict:

Resolving Conflicts Between Roles
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The account owner can set roles for both multiproduct and |product name|
scope, and it is important to understand how any potential conflicts between
these roles are resolved. When two roles appear to conflict, the role that
provides the more extensive permissions takes precedence. Therefore, admin
roles take precedence over observer and creator roles, because admin roles
provide more permissions.

The following table shows two examples of how potential conflicts between user
roles in the Control Panel are resolved.


.. list-table:: **Example of resolving permissions**
   :widths: 10 10 40
   :header-rows: 1

   * - Permission configuration
     - Control Panel permission view
     - Control Panel admin capabilities
   * - User is assigned the following roles: multiproduct **observer** and
       |product name| **admin**
     - Appears that the user has only the multiproduct **observer** role
     - User can perform admin functions for |product name| only. The user has
       the **observer** role for the rest of the products.
   * - User is assigned to the following roles: multiproduct **admin** and
       |product name| **observer**
     - Appears that the user has only the multiprodcut **admin** role
     - User can perform admin functions for all of the products.
       The |product name| **observer** role is ignored.

RBAC Permissions Cross-reference to |product name| API Operations
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

API operations for |product name| may or may not be available to all roles. To
see which operations are permitted to invoke which calls, please review the
:how-to:`Permissions Matrix for Role-Based Access Control (RBAC) \
<permissions-matrix-for-role-based-access-control-rbac>`.
