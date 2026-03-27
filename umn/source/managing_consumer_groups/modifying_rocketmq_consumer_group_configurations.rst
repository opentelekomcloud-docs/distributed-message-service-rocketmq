:original_name: hrm-ug-015.html

.. _hrm-ug-015:

Modifying RocketMQ Consumer Group Configurations
================================================

After creating a consumer group, you can modify its configuration as required.

Prerequisite
------------

:ref:`A consumer group <hrm-ug-013>` has been created.


Modifying RocketMQ Consumer Group Configurations
------------------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Consumer Groups**.

#. Modify consumer group parameters in either of the following ways:

   -  In the row containing the consumer group whose parameters you want to modify, click **Edit**.
   -  Click a consumer group and then click **Edit** in the upper right corner of the consumer group details page.

#. Modify consumer group parameters by referring to :ref:`Table 1 <hrm-ug-015__table186364410350>`.

   .. _hrm-ug-015__table186364410350:

   .. table:: **Table 1** Consumer group parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                   |
      +===================================+===============================================================================================================================================================================================================================================================+
      | Maximum Retries                   | Maximum number of times that messages are resent upon consumption failures. For example, if this parameter is set to 3, a message can be delivered for a maximum of 4 times. One time is for delivering the original message, and 3 times are for redelivery. |
      |                                   |                                                                                                                                                                                                                                                               |
      |                                   | Value range: 1-16                                                                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                                               |
      |                                   | Modifying this parameter takes effect only after the consumer group is restarted. To avoid infinite retries, set a proper value as required. A large value may increase the system pressure.                                                                  |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Broadcast                         | Indicates whether messages are broadcast.                                                                                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                               |
      |                                   | If this option is enabled, each message is retrieved by all consumers in the consumer group. If this option is disabled, each message is retrieved by only one consumer in the consumer group.                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Orderly                           | This parameter is mandatory when the RocketMQ instance version is 5.x.                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                               |
      |                                   | If this option is enabled, consumers consume messages in sequence.                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                               |
      |                                   | Orderly consumption ensures sequential consumption by message sending. In this case, earlier messages are consumed before later messages                                                                                                                      |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
