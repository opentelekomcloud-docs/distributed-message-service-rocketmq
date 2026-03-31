:original_name: hrm-ug-009.html

.. _hrm-ug-009:

Viewing RocketMQ Topic Details
==============================

After a topic is created, you can query its configuration and status on the console.

Prerequisites
-------------

-  A RocketMQ instance has been created.
-  A topic has been :ref:`created <hrm-ug-008>`.

Viewing Topic Details
---------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Topics**.

#. Click the desired topic name to go to the topic details page.

   The upper part of the topic details page shows the topic name, description, and message type. The lower part of the topic details page shows the total number of messages, deleted messages, topic's consumption status, and user permissions of this topic.


   .. figure:: /_static/images/en-us_image_0000002390875281.png
      :alt: **Figure 1** Topic details

      **Figure 1** Topic details

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
