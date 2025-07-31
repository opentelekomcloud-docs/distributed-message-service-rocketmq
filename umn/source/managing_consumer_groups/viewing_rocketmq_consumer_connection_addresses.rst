:original_name: hrm_ug_045.html

.. _hrm_ug_045:

Viewing RocketMQ Consumer Connection Addresses
==============================================

The consumer connection addresses are the message consumption client addresses. The connection addresses of a connected client can be viewed on the console.

Notes and Constraints
---------------------

A consumer's connection addresses can be viewed only when the consumer is connected to a RocketMQ instance.

Prerequisites
-------------

-  :ref:`A consumer group <hrm-ug-013>` has been created and there are consumers in the group.
-  :ref:`A topic <hrm-ug-008>` has been created.


Viewing RocketMQ Consumer Connection Addresses
----------------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane on the left, choose **Instance Diagnosis**.

#. For **Consumer Group**, select the group whose consumer connection address you want to view. Then click **Start Diagnosis**.

#. Locate the row containing the desired diagnosis record, and click **View**.

#. In the **Results** area, view the consumer connection address.


   .. figure:: /_static/images/en-us_image_0000002206558584.png
      :alt: **Figure 1** Consumer connection addresses

      **Figure 1** Consumer connection addresses

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
