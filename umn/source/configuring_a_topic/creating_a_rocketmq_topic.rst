:original_name: hrm-ug-008.html

.. _hrm-ug-008:

Creating a RocketMQ Topic
=========================

A topic is the basic unit for sending and receiving messages. After creating a RocketMQ instance, you must manually create a topic, and publish and subscribe to messages. A message producer sends messages to this topic. A message consumer consumes messages by subscribing to this topic.

Prerequisite
------------

A RocketMQ instance has been created.

Creating a Topic
----------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Click a RocketMQ instance name to go to the instance overview page.

#. In the navigation pane, choose **Instance** > **Topics**.

#. Click **Create Topic**.

#. Configure the topic name and other parameters by referring to\ :ref:`Table 1 <hrm-ug-008__table1385242712615>`.


   .. figure:: /_static/images/en-us_image_0000002390873325.png
      :alt: **Figure 1** Creating a topic

      **Figure 1** Creating a topic

   .. _hrm-ug-008__table1385242712615:

   .. table:: **Table 1** Topic parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                        |
      +===================================+====================================================================================================================================================================================================================+
      | Topic Name                        | Name of the topic.                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | A topic name must meet the following requirements:                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  Contains 3 to 64 characters.                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  Contains only letters, digits, percent signs (%), vertical bars (|), hyphens (-), and underscores (_).                                                                                                          |
      |                                   |                                                                                                                                                                                                                    |
      |                                   |    A percent (%) or vertical bar (|) contained in a topic name will be converted to an underscore (_) by Cloud Eye. For example, if a topic name is **test%01**, it will be displayed as **test_01** on Cloud Eye. |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  Cannot start with **rmq_sys\_**.                                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  Cannot be the same as the following strings:                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                    |
      |                                   |    -  TBW102                                                                                                                                                                                                       |
      |                                   |    -  SCHEDULE_TOPIC_XXXX                                                                                                                                                                                          |
      |                                   |    -  BenchmarkTest                                                                                                                                                                                                |
      |                                   |    -  RMQ_SYS_TRANS_HALF_TOPIC                                                                                                                                                                                     |
      |                                   |    -  RMQ_SYS_TRACE_TOPIC                                                                                                                                                                                          |
      |                                   |    -  RMQ_SYS_TRANS_OP_HALF_TOPIC                                                                                                                                                                                  |
      |                                   |    -  TRANS_CHECK_MAX_TIME_TOPIC                                                                                                                                                                                   |
      |                                   |    -  SELF_TEST_TOPIC                                                                                                                                                                                              |
      |                                   |    -  OFFSET_MOVED_EVENT                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  The topic name must be unique. Otherwise, the topic cannot be created.                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | **Once the topic is created, you cannot modify its name.**                                                                                                                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Message Type                      | Select the message type.                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Options:                                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | -  **Normal**: Messages that do not have any features of scheduled messages, ordered messages, or transactional messages.                                                                                          |
      |                                   | -  **Scheduled**: Messages that are delivered to consumers only after a specific period after being sent from producers to DMS for RocketMQ.                                                                       |
      |                                   | -  **Ordered**: Messages that are consumed in the exact order that they are produced.                                                                                                                              |
      |                                   | -  **Transactional**: Messages that achieve eventual consistency, delivering distributed transaction processing similar to X/Open XA.                                                                              |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | Default: **Normal**                                                                                                                                                                                                |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Topic description.                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                    |
      |                                   | The value contains 0 to 200 characters.                                                                                                                                                                            |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
