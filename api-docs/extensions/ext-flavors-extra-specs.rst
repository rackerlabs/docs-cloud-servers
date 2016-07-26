.. _flavors-extra-specs-extension:

=============================
Flavors Extra Specs Extension
=============================

The flavors extra spec extension adds the ``OS-FLV-WITH-EXT-SPECS:extra_specs``
attribute on flavors, providing additional information about the flavor such as
identifying the flavor class.

Changes to Get flavor details API operation
-------------------------------------------

A **GET** request on the **/flavors/{id}** resource returns the
``OS-FLV-WITH-EXT-SPECS:extra_specs`` extended attribute.


For an example, see the following operation:

:ref:`Show flavor with extra specs <get-show-flavor-with-extra-specs-flavors-flavor-id>`

