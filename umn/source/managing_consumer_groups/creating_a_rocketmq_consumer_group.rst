:original_name: hrm-ug-013.html

.. _hrm-ug-013:

Creating a RocketMQ Consumer Group
==================================

A consumer group is a group of consumers with the same behavior and is used to manage and maintain message retrieval. A consumer can manage a type of messages using a consumer group.

At least one RocketMQ consumer group is automatically created.

Prerequisites
-------------

A RocketMQ instance has been created.


Creating a RocketMQ Consumer Group
----------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Consumer Groups**.

#. Click **Create Consumer Group**.

#. Configure the consumer group name and other parameters by referring to :ref:`Table 1 <hrm-ug-013__table186364410350>`.

   .. _hrm-ug-013__table186364410350:

   .. table:: **Table 1** Consumer group parameters

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                 |
      +===================================+=============================================================================================================================================================================================================+
      | Consumer Group Name               | Name of the consumer group.                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                             |
      |                                   | A consumer group must meet the following requirements:                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                             |
      |                                   | -  Contains 3 to 64 characters.                                                                                                                                                                             |
      |                                   | -  Contains only letters, digits, percent signs (%), vertical bars (|), hyphens (-), and underscores (_).                                                                                                   |
      |                                   |                                                                                                                                                                                                             |
      |                                   | Once the consumer group is created, you cannot modify its name.                                                                                                                                             |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Brokers                           | This parameter is mandatory when the RocketMQ instance version is 4.8.0.                                                                                                                                    |
      |                                   |                                                                                                                                                                                                             |
      |                                   | Select one or multiple brokers to create consumer groups as required. The consumer groups are automatically created.                                                                                        |
      |                                   |                                                                                                                                                                                                             |
      |                                   | Once the consumer group is created, you cannot modify its brokers.                                                                                                                                          |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Maximum Retries                   | Maximum number of retry attempts allowed for normal messages.                                                                                                                                               |
      |                                   |                                                                                                                                                                                                             |
      |                                   | Value range: 1-16                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                             |
      |                                   | For ordered retrievals, this limit can be configured by using the **setMaxReconsumeTimes** method.                                                                                                          |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Broadcast                         | Indicates whether messages are broadcast.                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                             |
      |                                   | If this option is enabled, each message is retrieved by all consumers in the consumer group. If this option is disabled, each message is retrieved by only one consumer in the consumer group.              |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Orderly                           | This parameter is mandatory when the RocketMQ instance version is 5.x.                                                                                                                                      |
      |                                   |                                                                                                                                                                                                             |
      |                                   | If this option is enabled, consumers consume messages in sequence. Orderly consumption ensures sequential consumption by message sending. In this case, earlier messages are consumed before later messages |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   View **Consumption Model** on the consumer group list page once a v4.8.0 consumer group is created.

   -  CLUSTERING: cluster consumption mode. RocketMQ consumes any message by any consumer in the consumer group.
   -  BROADCASTING: broadcast consumption mode. RocketMQ pushes each message to all consumers in the consumer group to ensure that the message is consumed by each consumer.

   **Consumption Model** is **--** when the consumer group is offline.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
