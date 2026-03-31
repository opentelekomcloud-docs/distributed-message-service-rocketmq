:original_name: hrm-ug-009.html

.. _hrm-ug-009:

Viewing RocketMQ Topic Details
==============================

After a topic is created, you can query its configuration and status on the console.

Prerequisite
------------

:ref:`A topic has been created <hrm-ug-008>`.

Viewing Topic Details
---------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Click a RocketMQ instance name to go to the instance overview page.

#. In the navigation pane, choose **Instance** > **Topics**.

#. Click the desired topic name to go to the topic details page.

   The upper part of the topic details page shows the topic name, description, and message type. The lower part of the topic details page shows the total number of messages, deleted messages, message consumption status, and user permissions of this topic.


   .. figure:: /_static/images/en-us_image_0000002390875281.png
      :alt: **Figure 1** Topic details

      **Figure 1** Topic details

   .. note::

      The user permission information is displayed only when you create an instance or enable ACL on the overview page of the instance.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
