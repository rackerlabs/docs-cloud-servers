.. _api-operations-images:

Image operations
~~~~~~~~~~~~~~~~

This section covers the following image operations:

Image Operations
	- :ref:`List images <get-retrieve-list-of-images-images>`
	- :ref:`List images with details <get-retrieve-list-of-images-with-details-images-detail>`
	- :ref:`Show image details <get-retrieve-image-details-images-image-id>`
	- :ref:`Delete image <delete-delete-image-images-image-id>`

Image Metadata Operations
	- :ref:`List image metadata <get-retrieve-image-metadata-for-specified-image-images-image-id-metadata>`
	- :ref:`Set image metadata <post-set-image-metadata-for-specified-image-images-image-id-metadata>`
	- :ref:`List image metadata items <get-retrieve-image-metadata-item-for-specified-image-images-image-id-metadata-key>`
	- :ref:`Update image metadata item <put-set-image-metadata-item-for-specified-image-images-image-id-metadata-key>`
	- :ref:`Delete image metadata item <delete-delete-image-metadata-item-for-specified-image-images-image-id-metadata-key>`

Scheduled Images Operations
	- :ref:`Enable scheduled images<post-enable-scheduled-images-servers-server-id-rax-si-scheduled-image>`
	- :ref:`Show scheduled images <get-show-scheduled-images-servers-server-id-rax-si-scheduled-image>`
	- :ref:`Disable scheduled images <delete-disable-scheduled-images-servers-server-id-rax-si-scheduled-image>`


.. note::
   To create an image, see :ref:`Server Action Create Image<api-operations-svr-basic>`.

.. include:: methods/get-retrieve-list-of-images-images.rst
.. include:: methods/get-retrieve-list-of-images-with-details-images-detail.rst
.. include:: methods/get-retrieve-image-details-images-image-id.rst
.. include:: methods/delete-delete-image-images-image-id.rst

.. IMAGE METADATA OPS

.. include:: methods/get-retrieve-image-metadata-for-specified-image-images-image-id-metadata.rst
.. include:: methods/post-set-image-metadata-for-specified-image-images-image-id-metadata.rst
.. include:: methods/get-retrieve-image-metadata-item-for-specified-image-images-image-id-metadata-key.rst
.. include:: methods/put-set-image-metadata-item-for-specified-image-images-image-id-metadata-key.rst
.. include:: methods/delete-delete-image-metadata-item-for-specified-image-images-image-id-metadata-key.rst

.. SCHED IMAGE OPS

.. include:: methods/post-enable-scheduled-images-servers-server-id-rax-si-scheduled-image.rst
.. include:: methods/get-show-scheduled-images-servers-server-id-rax-si-scheduled-image.rst
.. include:: methods/delete-disable-scheduled-images-servers-server-id-rax-si-scheduled-image.rst