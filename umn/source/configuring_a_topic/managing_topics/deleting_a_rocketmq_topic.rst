:original_name: hrm-ug-011.html

.. _hrm-ug-011:

Deleting a RocketMQ Topic
=========================

If a topic is no longer used, you can delete it to release resources by referring to this section.

Topics can be deleted only when the instance is in the **Running** state.

Notes and Constraints
---------------------

Deleting a topic clears the topic data permanently. Related services will be affected.

Prerequisite
------------

:ref:`A topic has been created <hrm-ug-008>`.

Deleting a Topic
----------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Click a RocketMQ instance name to go to the instance overview page.

#. In the navigation pane, choose **Instance** > **Topics**.

#. Delete topics in any of the following ways:

   **Exercise caution when deleting topics because data will be lost.**

   -  In the row containing the topic to be deleted, click **Delete**.
   -  Click a topic to go to the topic details page and then click **Delete** in the upper right corner.
   -  To delete multiple topics at a time, select the topics, and click **Delete Topic** above the topic list.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
