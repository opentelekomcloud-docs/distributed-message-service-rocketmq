:original_name: hrm-ug-059.html

.. _hrm-ug-059:

Changing RocketMQ Message Retention Period
==========================================

Message retention period is a period that messages in a topic are retained for. Consumers must retrieve messages before this period ends. Otherwise, the messages will be deleted and can no longer be retrieved.

The retention period of normal messages and dead letter messages is controlled by and changes with the message retention period.

After creating an instance, you can modify its message retention period based on service requirements. Changing the retention period does not restart the instance. The default message retention period is 48 hours.

Prerequisite
------------

A RocketMQ instance has been created.


Changing RocketMQ Message Retention Period
------------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. Click |image3| next to **Message Retention**.

   Enter an integer in the range from 1 to 720.

#. Click |image4|. The modification result is displayed in the upper right corner of the page.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0000001093972624.png
.. |image4| image:: /_static/images/en-us_image_0000002111665312.png
