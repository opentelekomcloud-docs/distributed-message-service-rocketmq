:original_name: hrm-ug-089.html

.. _hrm-ug-089:

Exporting RocketMQ Topics
=========================

The topic list information can be exported on the RocketMQ console.

Notes and Constraints
---------------------

The basic information about a topic, such as the topic name and description, can be exported. Changes or migration of message data in the topic is not involved.

Prerequisite
------------

:ref:`A topic has been created <hrm-ug-008>`.

Procedure
---------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Click a RocketMQ instance name to go to the instance overview page.

#. In the navigation pane, choose **Instance** > **Topics**.

#. Export a topic list in either of the following ways:

   -  Select the desired topic, choose **Export** > **Export selected data to an XLSX file** to export a specified topic list.
   -  Choose **Export** > **Export all data to an XLSX file** to export the list of all topics.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
