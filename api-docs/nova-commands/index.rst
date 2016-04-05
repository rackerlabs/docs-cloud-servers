.. meta
   :description: Nova client command Reference
   :keywords: Rackspace, Cloud Servers Nova Client, Nova Commands
   
.. _nova-reference:

Nova client reference
---------------------

Use the following nova client commands to perform admin API operations:

Authentication and Service Catalog

+--------------------+---------------------------+-----------------------+------------+
| Command            | Description               | Reference             | Works?     |
+====================+===========================+=======================+============+
| credentials        | Shows user credentials    | :ref:`Credentials \   | Yes        |
|                    | returned from             | <nc-get-credentials>` |            |
|                    | an authentication request.|                       |            |
+--------------------+---------------------------+-----------------------+------------+
| endpoints          | Lists endpoints for the   | :ref:`Endpoints \     | Yes        |
|                    | account.                  | <nc-get-endpoints>`   |            |
+--------------------+---------------------------+-----------------------+------------+

Limits

+--------------------+---------------------------+--------------------------+------------+
| Command            | Description               | Reference                | Works?     |
+====================+===========================+==========================+============+
| absolute-limits    | Lists absolute limits for | :ref:`Absolute limits \  | Yes        |
|                    | a user.                   | <nc-get-absolute-limits>`|            |
+--------------------+---------------------------+--------------------------+------------+
| rate-limits        | Lists rate limits for a   | :ref:`Rate limits \      | Yes        |
|                    | user.                     | <nc-get-rate-limits>`    |            |
+--------------------+---------------------------+--------------------------+------------+

Servers

+--------------------+---------------------------+----------------------+------------+
| Command            | Description               | Reference            | Works?     |
+====================+===========================+======================+============+
| list               | Lists active servers.     | :ref:`List servers \ | Yes        |
|                    |                           | <nc-list-servers>`   |            |
|                    |                           |                      |            |
|                    |                           |                      |            |
+--------------------+---------------------------+----------------------+------------+
| boot               | Boots a new server.       | :ref:`Boot server \  | Disabled   |
|                    |                           | <nc-boot-server>`    |            |
|                    |                           |                      |            |
|                    |                           |                      |            |
|                    |                           |                      |            |
+--------------------+---------------------------+----------------------+------------+
| show               | Shows details for a       | :ref:`Show server \  | Yes        |
|                    | specified server.         | details \            |            |
|                    |                           | <nc-show-server>`    |            |
|                    |                           |                      |            |
+--------------------+---------------------------+----------------------+------------+
| rename             | Renames a server.         | :ref:`Rename server \| Yes        |
|                    |                           | <nc-rename-server>`  |            |
|                    |                           |                      |            |
|                    |                           |                      |            |
+--------------------+---------------------------+----------------------+------------+
| delete             | Immediately shuts down    | :ref:`Delete server \| Disabled   |
|                    | and deletes a server.     | <nc-delete-server>`  |            |
|                    |                           |                      |            |
|                    |                           |                      |            |
+--------------------+---------------------------+----------------------+------------+

Server Actions

+--------------------+---------------------------+----------------------+------------+
| Command            | Description               | Reference            | Works?     |
+====================+===========================+======================+============+
| root-password      | Changes the root password | :ref:`Change root \  | Yes        |
|                    | for a server.             | password \           |            |
|                    |                           | <nc-sa-change-passwo\|            |
|                    |                           | rd>`                 |            |
+--------------------+---------------------------+----------------------+------------+
| reboot             | Reboots a server.         | :ref:`Reboot \       | Disabled   |
|                    |                           | server \             |            |
|                    |                           | <nc-sa-reboot-server\|            |
|                    |                           | >`                   |            |
+--------------------+---------------------------+----------------------+------------+
| rebuild            | Shuts down, reimages, and | :ref:`Rebuild \      | Yes        |
|                    | reboots a server.         | server \             | (issues    |
|                    |                           | <nc-sa-rebuild>`     | with perms)|
+--------------------+---------------------------+----------------------+------------+
| resize             | Resizes a server.         | :ref:`Resize \       | Yes        |
|                    |                           | server \             |            |
|                    |                           | <nc-sa-resize>`      |            |
+--------------------+---------------------------+----------------------+------------+
| resize-confirm     | Confirms a resized        | :ref:`Confirm \      | Yes        |
|                    | server.                   | server resize \      |            |
|                    |                           | <nc-sa-confirm-resiz\|            |
|                    |                           | e>`                  |            |
+--------------------+---------------------------+----------------------+------------+
| resize-revert      | Reverts a previous resize | :ref:`Revert \       | Yes        |
|                    | and returns to the        | server resize \      |            |
|                    | previous VM.              | <nc-sa-revert-resize\|            |
|                    |                           | >`                   |            |
+--------------------+---------------------------+----------------------+------------+
| rescue             | Rescues a server.         | :ref:`Rescue \       | Disabled   |
|                    |                           | server \             |            |
|                    |                           | <nc-sa-rescue>`      |            |
+--------------------+---------------------------+----------------------+------------+
| unrescue           | Unrescues a server.       | :ref:`Unrescue \     | Disabled   |
|                    |                           | server \             |            |
|                    |                           | <nc-sa-unrescue>`    |            |
+--------------------+---------------------------+----------------------+------------+
| image-create       | Creates a new             | :ref:`Create \       | Error      |
|                    | image by taking a         | server \             |            |
|                    | snapshot of a running     | <nc-sa-create-image>`|            |
+--------------------+---------------------------+----------------------+------------+
| diagnostics        | Gets server diagnostics.  | :ref:`Diagnostics \  | Yes        |
|                    |                           | <nc-sa-diagnostics>` |            |
+--------------------+---------------------------+----------------------+------------+
| lock               | Locks a server.           | :ref:`Lock server \  | Yes        |
|                    |                           | <nc-sa-lock-server>` |            |
+--------------------+---------------------------+----------------------+------------+
| unlock             | Unlocks a server.         | :ref:`Unlock \       | Yes        |
|                    |                           | server \             |            |
|                    |                           | <nc-sa-unlock-server\|            |
|                    |                           | >`                   |            |
+--------------------+---------------------------+----------------------+------------+
| migrate            | Migrates a server.        | :ref:`Migrate \      | Yes        |
|                    |                           | server \             |            |
|                    |                           | <nc-sa-migrate-serve\|            |
|                    |                           | r>`                  |            |
+--------------------+---------------------------+----------------------+------------+
| pause              | Pauses a server.          | :ref:`Pause \        | Needed?    |
|                    |                           | server \             |            |
|                    |                           | <nc-sa-pause-server>`|            |
+--------------------+---------------------------+----------------------+------------+
| unpause            | Unpauses a server.        | :ref:`Unpause \      | Yes        |
|                    |                           | server \             |            |
|                    |                           | <nc-sa-unpause-serve\|            |
|                    |                           | r>`                  |            |
+--------------------+---------------------------+----------------------+------------+
| reset-state        | Resets the state of an    | :ref:`Reset state \  | Yes        |
|                    | instance.                 | <nc-sa-reset-state>` |            |
+--------------------+---------------------------+----------------------+------------+
| resume             | Resumes a server.         | :ref:`Resume server \| Yes        |
|                    |                           | <nc-sa-resume-server\|            |
|                    |                           | >`                   |            |
+--------------------+---------------------------+----------------------+------------+
| ssh                | SSHs into a server.       | :ref:`SSH to server \| Yes        |
|                    |                           | <nc-sa-ssh>`         |            |
+--------------------+---------------------------+----------------------+------------+
| start              | Starts a server.          | :ref:`Start server \ | Yes        |
|                    |                           | <nc-sa-start-server>`|            |
+--------------------+---------------------------+----------------------+------------+
| stop               | Stops a server.           | :ref:`Stop server \  | Yes        |
|                    |                           | <nc-sa-stop-server>` |            |
+--------------------+---------------------------+----------------------+------------+
| suspend            | Suspends a server.        | :ref:`Suspend server | Yes        |
|                    |                           | <nc-sa-suspend-serve\|            |
|                    |                           | r>`                  |            |
+--------------------+---------------------------+----------------------+------------+

Images

+--------------------+---------------------------+--------------------+------------+
| Command            | Description               | Reference          | Works?     |
+====================+===========================+====================+============+
| image-list         | Lists available images to | :ref:`List images \| Yes        |
|                    | boot from.                | <nc-list-images>`  |            |
+--------------------+---------------------------+--------------------+------------+
| image-show         | Shows details for a       | :ref:`Get image \  | Yes        |
|                    | specified image.          | details \          |            |
|                    |                           | <nc-get-image-deta\|            |
|                    |                           | ils>`              |            |
+--------------------+---------------------------+--------------------+------------+
| image-delete       | Deletes an image.         | :ref:`Delete image\| Works      |
|                    |                           | <nc-delete-image>` |            |
+--------------------+---------------------------+--------------------+------------+

Metadata

+--------------------+---------------------------+--------------------+------------+
| Command            | Description               | Reference          | Works?     |
+====================+===========================+====================+============+
| image-meta         | Sets or deletes specified | :ref:`Set or delet\| Not tested |
|                    | metadata on an image.     | e image metadata \ |            |
|                    |                           | <nc-image-meta>`   |            |
+--------------------+---------------------------+--------------------+------------+
| meta               | Sets or deletes specified | :ref:`Set or delet\| Yes        |
|                    | metadata on a server.     | e server metadata \|            |
|                    |                           | <nc-meta>`         |            |
+--------------------+---------------------------+--------------------+------------+

Flavors

+--------------------+---------------------------+--------------------+------------+
| Command            | Description               | Reference          | Works?     |
+====================+===========================+====================+============+
| flavor-list        | Lists available           | :ref:`List flavors\| Yes        |
|                    | flavors.                  | <nc-list-flavors>` |            |
+--------------------+---------------------------+--------------------+------------+
| flavor-show        | Shows details for a       | :ref:`Get flavor d\| Yes        |
|                    | specified flavor.         | etails \           |            |
|                    |                           | <nc-get-flavor-det\|            |
|                    |                           | ails>`             |            |
+--------------------+---------------------------+--------------------+------------+

Console

+--------------------+---------------------------+--------------------+------------+
| Command            | Description               | Reference          | Works?     |
+====================+===========================+====================+============+
| get-vnc-console    | Gets a VNC console to a   | :ref:`Get VNC cons\| Disabled   |
|                    | server. (xvpvnc)          | ole \              |            |
|                    |                           | <nc-get-vnc-consol\|            |
|                    |                           | e>`                |            |
+--------------------+---------------------------+--------------------+------------+

Hosts

+--------------------+---------------------------+---------------------+------------+
| Command            | Description               | Reference           | Works?     |
+====================+===========================+=====================+============+
| host-action        | Performs a power action   | :ref:`Perform host \| Error      |
|                    | on a host.                | action \            |            |
|                    |                           | <nc-host-action>`   |            |
+--------------------+---------------------------+---------------------+------------+
| host-describe      | Describes a specified     | :ref:`Describe host\| Yes        |
|                    | host.                     | <nc-describe-host>` |            |
+--------------------+---------------------------+---------------------+------------+
| host-list          | Lists all hosts by        | :ref:`List hosts \  | Yes        |
|                    | service.                  | <nc-list-hosts>`    |            |
+--------------------+---------------------------+---------------------+------------+
| host-update        | Updates host settings.    | :ref:`Update host\  | Yes        |
|                    |                           | <nc-update-host>`   |            |
+--------------------+---------------------------+---------------------+------------+

Hypervisors

+--------------------+---------------------------+--------------------+------------+
| Command            | Description               | Reference          | Works?     |
+====================+===========================+====================+============+
| hypervisor-list    | Lists hypervisors.        | :ref:`List hypervi\| Yes        |
|                    |                           | sors \             |            |
|                    |                           | <nc-list-hyperviso\|            |
|                    |                           | rs>`               |            |
+--------------------+---------------------------+--------------------+------------+
| hypervisor-servers | Lists instances that      | :ref:`List servers\| Yes        |
|                    | belong to specified       | on hypervisor \    |            |
|                    | hypervisors.              | <nc-list-hyperviso\|            |
|                    |                           | r-servers>`        |            |
+--------------------+---------------------------+--------------------+------------+
| hypervisor-show    | Shows details for the     | :ref:`Get hypervis\| Error      |
|                    | specified hypervisor.     | or details \       |            |
|                    |                           | <nc-show-hyperviso\|            |
|                    |                           | r>`                |            |
+--------------------+---------------------------+--------------------+------------+

Quotas

+--------------------+---------------------------+--------------------+------------+
| Command            | Description               | Reference          | Works?     |
+====================+===========================+====================+============+
| quota-class-show   | Lists quotas for a quota  | :ref:`List quotas \| Yes        |
|                    | class.                    | for a class        |            |
|                    |                           | <nc-list-quotas-qu\|            |
|                    |                           | ota-class>`        |            |
+--------------------+---------------------------+--------------------+------------+
| quota-class-update | Updates quotas for a quota| :ref:`Update quota\| Yes        |
|                    | class.                    | s for a class \    |            |
|                    |                           | <nc-update-quota-q\|            |
|                    |                           | uota-class>`       |            |
|                    |                           |                    |            |
+--------------------+---------------------------+--------------------+------------+
| quota-defaults     | Lists default quotas for  | :ref:`List defaul\ | Yes        |
|                    | a tenant.                 | t quotas for tenan\|            |
|                    |                           | t \                |            |
|                    |                           | <nc-list-default-q\|            |
|                    |                           | uotas>`            |            |
+--------------------+---------------------------+--------------------+------------+
| quota-show         | Lists quotas for a        | :ref:`List quotas \| Yes        |
|                    | tenant.                   | <nc-list-quotas>`  |            |
+--------------------+---------------------------+--------------------+------------+
| quota-update       | Updates quotas for a      | :ref:`Update quota\| Yes        |
|                    | tenant.                   | <nc-update-quota>` |            |
+--------------------+---------------------------+--------------------+------------+
| usage-list         | Lists usage data for all  | :ref:`List usage d\| Broken     |
|                    | tenants.                  | ata \              |            |
|                    |                           | <nc-list-usage-dat\|            |
|                    |                           | a>`                |            |
+--------------------+---------------------------+--------------------+------------+

Services

+--------------------+---------------------------+---------------------+------------+
| Command            | Description               | Reference           | Works?     |
+====================+===========================+=====================+============+
| service-config     | Shows flag configurations | :ref:`Show service \| Needs to   |
|                    | for a specified service.  | configuration \     | be fixed   |
|                    |                           | <nc-show-service-co\|            |
|                    |                           | nfig>`              |            |
+--------------------+---------------------------+---------------------+------------+
| service-details    | Shows detailed            | :ref:`Show service \| Error      |
|                    | information for a         | details \           |            |
|                    | specified service.        | <nc-show-service-de\|            |
|                    |                           | tails>`             |            |
+--------------------+---------------------------+---------------------+------------+
| service-disable    | Disables a specified      | :ref:`Disable servi\| Yes        |
|                    | service.                  | ce \                |            |
|                    |                           | <nc-disable-service\|            |
|                    |                           | >`                  |            |
+--------------------+---------------------------+---------------------+------------+
| service-enable     | Enables a specified       | :ref:`Enable servic\| Yes        |
|                    | service.                  | e \                 |            |
|                    |                           | <nc-enable-service>`|            |
+--------------------+---------------------------+---------------------+------------+
| service-list       | Lists available service   | :ref:`List services\| Yes        |
|                    | attributes.               | <nc-list-services>` |            |
+--------------------+---------------------------+---------------------+------------+
| service-servers    | Lists servers that belong | :ref:`List servers \| Error      |
|                    | to a specified service.   | for a service \     |            |
|                    |                           | <nc-list-service-se\|            |
|                    |                           | rvers>`             |            |
+--------------------+---------------------------+---------------------+------------+
| service-show       | Shows information for a   | :ref:`Show service \| Yes        |
|                    | specified service.        | information \       |            |
|                    |                           | <nc-show-service>`  |            |
+--------------------+---------------------------+---------------------+------------+
| service-version    | Shows the version for the | :ref:`Show service \| Yes        |
|                    | specified service.        | version \           |            |
|                    |                           | <nc-show-service-ve\|            |
|                    |                           | rsion>`             |            |
+--------------------+---------------------------+---------------------+------------+


.. toctree::
   :maxdepth: 1

   nc-auth
   nc-limits
   nc-servers
   nc-server-actions
   nc-images
   nc-metadata
   nc-flavors
   nc-console
   nc-hosts
   nc-hypervisors
   nc-quotas
   nc-services
