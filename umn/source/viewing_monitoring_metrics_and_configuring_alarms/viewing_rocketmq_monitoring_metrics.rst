:original_name: hrm-ug-019.html

.. _hrm-ug-019:

Viewing RocketMQ Monitoring Metrics
===================================

Cloud Eye monitors RocketMQ instance metrics in real time. You can view these metrics on the console.

Prerequisites
-------------

A RocketMQ instance has been created.

Viewing RocketMQ Metrics
------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. Choose **Monitoring** in the navigation pane.

#. View monitoring data by the instance, brokers, topics, consumer groups, and dead letter queues.

   Monitoring data by broker is displayed only for v4.8.0.

#. (Optional) Click **View details** on the **By Instance**, **By Broker**, **By Topic**, **By Consumer Group**, or **By Dead Letter Queue** tab page to go to the Cloud Eye console.

   On the instance list page, you can also click **View Metric** in the row containing the desired instance to go to the Cloud Eye console.

   On the Cloud Eye console, you can select metrics and rearrange their order.

   For example, if you only need to view the **Created Messages** and **Retrieved Messages** metrics on the **By Instance** tab page, do as follows:

   a. On the **By Instance** tab page, click **Select Metric**.
   b. Select **Created Messages** and **Retrieved Messages**, and click **OK**.
   c. Drag and drop the selected metrics to desired locations to rearrange the order.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
