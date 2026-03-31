:original_name: hrm-ug-019.html

.. _hrm-ug-019:

Viewing RocketMQ Monitoring Metrics
===================================

Cloud Eye monitors RocketMQ instance metrics in real time. You can view these metrics on the console.

Prerequisite
------------

A RocketMQ instance has been created.

Viewing RocketMQ Metrics
------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. View the instance metrics in any of the following ways:

   -  **View all monitoring data:** After a RocketMQ instance name, click **View Metric**. On the Cloud Eye console, view the metrics. Metric data is reported to Cloud Eye every minute.
   -  **View all monitoring data:** Click a RocketMQ instance name to go to the instance overview page. In the navigation pane, choose **Monitoring**. On the displayed page, view the monitoring data. The data is updated every minute.

#. View monitoring data by the instance, topics, consumer groups, and dead letter queues.

#. (Optional) Click **View details** on the **By Instance**, **By Topic**, **By Consumer Group**, or **By Dead Letter Queue** tab page to go to the Cloud Eye console.

   On the Cloud Eye console, you can select metrics and rearrange their order.

   For example, if you only need to view the **Created Messages** and **Retrieved Messages** metrics on the **By Instance** tab page, do as follows:

   a. On the **By Instance** tab page, click **Select Metric**.
   b. Select **Created Messages** and **Retrieved Messages**, and click **OK**.
   c. Drag and drop the selected metrics to desired locations to rearrange the order.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
