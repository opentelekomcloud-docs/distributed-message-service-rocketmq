:original_name: hrm-ug-009.html

.. _hrm-ug-009:

Viewing RocketMQ Topic Details
==============================

After a topic is created, you can query its configuration and status on the console.

Prerequisites
-------------

-  A RocketMQ instance has been created.
-  A topic has been created.

Viewing Topic Details
---------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Topics**.

#. Click the desired topic name to go to the topic details page.

   -  RocketMQ 4.8.0: The upper part of the topic details page shows the topic name, the number of brokers, read queues, write queues, permissions, and description. The lower part of the topic details page shows the queue status on each broker, topic's consumption status, and authorization.
   -  RocketMQ 5.x: The upper part of the topic details page shows the topic name, message type, and description. The lower part of the topic details page shows the total number of messages, deleted messages, topic's consumption status, and authorization.


   .. figure:: /_static/images/en-us_image_0000002206696320.png
      :alt: **Figure 1** Topic details (RocketMQ 4.8.0)

      **Figure 1** Topic details (RocketMQ 4.8.0)


   .. figure:: /_static/images/en-us_image_0000002338224953.png
      :alt: **Figure 2** Topic details (RocketMQ 5.x)

      **Figure 2** Topic details (RocketMQ 5.x)

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
