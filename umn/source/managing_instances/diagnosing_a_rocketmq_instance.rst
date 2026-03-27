:original_name: hrm-ug-042.html

.. _hrm-ug-042:

Diagnosing a RocketMQ Instance
==============================

You can diagnose an instance to quickly locate faults when message consumption is slow or fails.

Prerequisites
-------------

-  :ref:`A consumer group has been created <hrm-ug-013>`, and there are consumers in the group.
-  :ref:`A topic <hrm-ug-008>` has been created.

Procedure
---------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane on the left, choose **Instance Diagnosis**.

#. Select a consumer group and click **Start Diagnose**.

   After the diagnosis is complete, a diagnosis record is displayed in the **Diagnosis Reports** area.

#. Click **View** to view the diagnosis result.

   The result contains the active status, number of consumers, subscription consistency, and message accumulation.


   .. figure:: /_static/images/en-us_image_0000002196081880.png
      :alt: **Figure 1** Diagnosis result

      **Figure 1** Diagnosis result

   .. note::

      If the consumer group is not online, the diagnosis is successful, but one abnormality is displayed.

Exporting Diagnosis Records
---------------------------

#. Log in to the console.

#. Click |image3| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image4| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Instance Diagnosis**.

#. Export instance diagnosis records in either of the following ways:

   -  Select the desired records and choose **Export** > **Export selected data to an XLSX file**.
   -  Choose **Export** > **Export all data to an XLSX file** to export all the records.

Deleting Diagnosis Records
--------------------------

#. Log in to the console.

#. Click |image5| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image6| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane on the left, choose **Instance Diagnosis**.

#. Use either of the following methods to delete diagnosis records:

   -  In the row containing the record you want to delete, click **Delete**.
   -  Select multiple records you want to delete and click **Delete** above the record list.

#. In the confirmation dialog box, click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0143929918.png
.. |image4| image:: /_static/images/en-us_image_0000001143589128.png
.. |image5| image:: /_static/images/en-us_image_0143929918.png
.. |image6| image:: /_static/images/en-us_image_0000001143589128.png
