:original_name: hrm-ug-082.html

.. _hrm-ug-082:

Adjusting Messages Sent/Received of a RocketMQ Instance
=======================================================

This function limits maximum message sending/reception traffic of the instance. Default ratio is 1:1. Adjust the write proportion for read-intensive services.

Prerequisite
------------

A RocketMQ 5.x instance is available.

Procedure
---------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. In the **Instance Information** area, click **Adjust Send/Receive Limit** next to **Messages Sent/Received**.

#. Adjust **Send (%)**.

   By default, the send and receive ratios are 50%. **Receive (%)** is adjusted accordingly.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
