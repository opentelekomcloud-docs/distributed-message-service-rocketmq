:original_name: hrm-ug-005.html

.. _hrm-ug-005:

Deleting a RocketMQ Instance
============================

Delete one or more RocketMQ instances at a time on the DMS for RocketMQ console.

Delete one or more RocketMQ instances at a time on the DMS console.

Prerequisites
-------------

The RocketMQ instance is in the **Running** or **Faulty** state.


Deleting a RocketMQ Instance
----------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Delete pay-per-use instances in either of the following ways:

   -  In the row containing the RocketMQ instance to be deleted, choose **More** > **Delete**.
   -  Click a RocketMQ instance to go to the instance details page. In the upper right corner, choose **More** > **Delete**.
   -  To delete multiple instances at a time, select the instances, and click **Delete** above the instance list.

#. In the **Delete Instance** dialog box, enter **DELETE** and click **OK**.

   It takes 1 to 60 seconds to delete a RocketMQ instance. **The instance data will be cleared.**

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
