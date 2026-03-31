:original_name: hrm-ug-014.html

.. _hrm-ug-014:

Viewing RocketMQ Consumer Group Details
=======================================

After a consumer group is created, you can query its configuration and status on the console.

Prerequisite
------------

-  A RocketMQ instance has been created.
-  A consumer group has been :ref:`created <hrm-ug-013>`.


Viewing RocketMQ Consumer Group Details
---------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Consumer Groups**.

#. Click the desired consumer group to go to the consumer group details page.

   In the upper part of the page, you can view the consumer group name, the maximum number of retries, orderly consumption, and whether messages are broadcast.

   In the lower part of the page, you can view the consumer group information, all topics subscribed by the consumer group, user permissions, and subscriptions.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
