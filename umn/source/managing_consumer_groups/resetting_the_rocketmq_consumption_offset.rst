:original_name: hrm-ug-051.html

.. _hrm-ug-051:

Resetting the RocketMQ Consumption Offset
=========================================

Resetting the consumption offset modifies the consumer position. Consumers consume messages from the modified positions.

Prerequisites
-------------

-  :ref:`A consumer group <hrm-ug-013>` has been created and there are consumers in the group.
-  :ref:`A topic <hrm-ug-008>` has been created.

Procedure
---------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Consumer Groups**.

#. In the row containing the desired consumer group, click **Reset Consumer Offset**.

#. Set parameters by referring to :ref:`Table 1 <hrm-ug-051__table138829501925>`.

   .. _hrm-ug-051__table138829501925:

   .. table:: **Table 1** Parameters for resetting the consumer offset

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                         |
      +===================================+=====================================================================================================================+
      | Topic Name                        | Select the topic whose consumer offset is to be reset.                                                              |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------+
      | Time                              | Select a time point. After the reset is complete, retrieval starts from this time point.                            |
      |                                   |                                                                                                                     |
      |                                   | -  **Custom**: Message consumption restarts from the customized time.                                               |
      |                                   | -  **Earliest**: Message consumption starts from the earliest time.                                                 |
      |                                   | -  **Latest**: Message consumption starts from the latest time. The messages before this time will not be consumed. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   **Messages may be consumed more than once after the offset is reset. Exercise caution when performing this operation.**

#. Click **Yes** in the confirmation dialog box. The consumer offset is reset.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
