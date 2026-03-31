:original_name: hrm-ug-013.html

.. _hrm-ug-013:

Creating a RocketMQ Consumer Group
==================================

A consumer group is a group of consumers with the same behavior and is used to manage and maintain message retrieval. A consumer can manage a type of messages using a consumer group.

If no consumer group is created, RocketMQ automatically creates one.

Prerequisite
------------

A RocketMQ instance has been created.


Creating a RocketMQ Consumer Group
----------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Click a RocketMQ instance name to go to the instance overview page.

#. In the navigation pane, choose **Instance** > **Consumer Groups**.

#. Click **Create Consumer Group**.

#. Configure the consumer group name and other parameters by referring to :ref:`Table 1 <hrm-ug-013__table186364410350>`.

   .. _hrm-ug-013__table186364410350:

   .. table:: **Table 1** Consumer group parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                          |
      +===================================+======================================================================================================================================================================================================================================+
      | Consumer Group Name               | Name of the consumer group.                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   | A consumer group must meet the following requirements:                                                                                                                                                                               |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   | -  Contains 3 to 64 characters.                                                                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   | -  Contains only letters, digits, percent signs (%), vertical bars (|), hyphens (-), and underscores (_).                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   |    A percent (%) or vertical bar (|) contained in a consumer group name will be converted to an underscore (_) by Cloud Eye. For example, if a consumer group name is **test%01**, it will be displayed as **test_01** on Cloud Eye. |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   | Once the consumer group is created, you cannot modify its name.                                                                                                                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Maximum Retries                   | Maximum number of retry attempts allowed for normal messages.                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   | Value range: 1-16                                                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   | For ordered retrievals, this limit can be configured by using the **setMaxReconsumeTimes** method.                                                                                                                                   |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Broadcast                         | Indicates whether messages are broadcast.                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   | If this option is enabled, each message is retrieved by all consumers in the consumer group. If this option is disabled, each message is retrieved by only one consumer in the consumer group.                                       |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Orderly                           | If this option is enabled, consumers consume messages in sequence. Orderly consumption ensures sequential consumption by message sending. In this case, earlier messages are consumed before later messages                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Description of the consumer group.                                                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                      |
      |                                   | Value range: 0-200 characters.                                                                                                                                                                                                       |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   When a consumer group is created, **Consumer Group Status** is displayed in the consumer group list. The value can be **Online** or **Offline**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
