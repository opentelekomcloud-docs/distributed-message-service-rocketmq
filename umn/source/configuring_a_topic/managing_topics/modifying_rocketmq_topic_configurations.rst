:original_name: hrm-ug-010.html

.. _hrm-ug-010:

Modifying RocketMQ Topic Configurations
=======================================

The topic description can be modified as required.

Prerequisites
-------------

-  A RocketMQ instance has been created.
-  A topic has been :ref:`created <hrm-ug-008>`.

Modifying Topic Information
---------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Topics**.

#. Modify topic parameters in either of the following ways:

   -  In the row containing the desired topic, click **Edit**.
   -  Click a topic to go to the topic details page and then click **Edit** in the upper right corner.

#. Modify topic parameters by referring to :ref:`Table 1 <hrm-ug-010__table186364410350>`.

   .. _hrm-ug-010__table186364410350:

   .. table:: **Table 1** Topic parameters

      +-----------------------------------+-----------------------------------+
      | Parameter                         | Description                       |
      +===================================+===================================+
      | Description                       | Topic description                 |
      |                                   |                                   |
      |                                   | 0-200 characters                  |
      +-----------------------------------+-----------------------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
