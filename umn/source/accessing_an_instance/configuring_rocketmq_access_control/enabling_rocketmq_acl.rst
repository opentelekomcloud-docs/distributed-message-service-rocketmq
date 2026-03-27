:original_name: hrm-ug-070.html

.. _hrm-ug-070:

Enabling RocketMQ ACL
=====================

RocketMQ instances support precise identification of producers and consumers through ACL (Access Control List)-based permission management. When ACL is enabled, message production and consumption require authentication.

Notes and Constraints
---------------------

Enabling ACL will disconnect clients without authentication configuration.

Prerequisite
------------

A RocketMQ instance has been created.


Enabling RocketMQ ACL
---------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the **Connection** area, click |image3| next to **ACL** to enable ACL.

   When ACL is enabled, **Users** is displayed in the navigation pane. You can configure ACL users by referring to :ref:`Configuring RocketMQ ACL Users <hrm-ug-035>`.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0000001191767177.png
