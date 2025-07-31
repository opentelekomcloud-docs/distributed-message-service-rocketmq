:original_name: hrm-ug-023.html

.. _hrm-ug-023:

Managing RocketMQ Dead Letters
==============================

When a message fails to be consumed and retried, RocketMQ does not discard it immediately, but forwards it to a specific dead letter queue. Messages in such a queue are dead letter messages. These messages can be sent and consumed again after faults are rectified. If they cannot be processed temporarily, they can be exported and saved in case of deletion after expiration.

Prerequisites
-------------

-  A RocketMQ instance and consumer groups have been created.

-  To query messages by message ID, you need the name of the consumer group to which the message belongs and the message ID.

   Message ID is the **MsgId** returned after the message is produced, for example, the content returned in :ref:`6 <hrm-ug-039__en-us_topic_0143117204_li54957760>`. Message IDs can be recorded in topic queries.

-  To query messages by message key, you need the name of the consumer group to which the message belongs and the message key.

   Message Key is the message key configured in :ref:`7 <hrm-ug-049__li0177144134310>`. Message keys can be recorded in topic queries.

How to Query Dead Letter Messages
---------------------------------

:ref:`Table 1 <hrm-ug-023__table9110996812>` compares three query modes.

.. _hrm-ug-023__table9110996812:

.. table:: **Table 1** Dead letter message query modes

   +-------------+-----------------------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Search By   | Search With           | Search In  | Description                                                                                                                                                                                   |
   +=============+=======================+============+===============================================================================================================================================================================================+
   | Group       | Group and time range  | Range      | Based on a consumer group and time range, you can obtain all the dead letter messages meeting the query criteria in batches. Due to the large number of messages, matching is more difficult. |
   +-------------+-----------------------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Message ID  | Group and message ID  | Exact mode | Based on a consumer group and message ID, you can accurately locate a dead letter message to obtain its attributes.                                                                           |
   +-------------+-----------------------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Message key | Group and message key | Fuzzy mode | Dead letter messages that contain specific keys can be queried by consumer group and message key.                                                                                             |
   +-------------+-----------------------+------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Querying Dead Letter Messages
-----------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Dead Letter Queues**.

#. Query dead letter messages in either of the following ways:

   -  By group: Select the name of the consumer group to be queried from the **Group** drop-down list. For **Stored**, select a time period.
   -  By message ID: Select the name of the consumer group to be queried from the **Group** drop-down list, enter the message ID of the dead letter message to be queried, and click **Search**.
   -  By message key: Select the name of the consumer group to be queried from the **Group** drop-down list, enter the message key of the dead letter message to be queried, and click **Search**.

Resending a Dead Letter Message
-------------------------------

Dead letter messages cannot be retrieved by consumers. Locate and rectify the fault, and then resend dead letter messages on the console.

#. Log in to the console.

#. Click |image3| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image4| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Dead Letter Queues**.

#. Resend dead letter messages in either of the following ways:

   **After a dead letter message is successfully resent, it still exists in the dead letter queue and will not be deleted. Do not retry resending a dead letter message to avoid repeated consumption.**

   -  In the row containing the dead letter message to be resent, click **Resend**.
   -  Select multiple dead letter messages to be resent and click **Resend**.

Exporting Dead Letter Messages
------------------------------

#. Log in to the console.

#. Click |image5| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image6| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Dead Letter Queues**.

#. Click **Export Message** in the row containing the desired message.

   The message will be exported in JSON format.

   .. note::

      To export multiple dead letter messages at a time, select them and click **Export Message** above the message list.

   :ref:`Table 2 <hrm-ug-023__table16357151111916>` describes the fields of an exported message.

   .. _hrm-ug-023__table16357151111916:

   .. table:: **Table 2** Message fields

      +-----------------------------------+----------------------------------------------------+
      | Parameter                         | Description                                        |
      +===================================+====================================================+
      | msg_id                            | Message ID.                                        |
      +-----------------------------------+----------------------------------------------------+
      | instance_id                       | Instance ID.                                       |
      +-----------------------------------+----------------------------------------------------+
      | topic                             | Topic name.                                        |
      +-----------------------------------+----------------------------------------------------+
      | store_timestamp                   | Time when the message is stored.                   |
      +-----------------------------------+----------------------------------------------------+
      | born_timestamp                    | Time when the message is generated.                |
      +-----------------------------------+----------------------------------------------------+
      | reconsume_times                   | Number of retry times.                             |
      +-----------------------------------+----------------------------------------------------+
      | body                              | Message body.                                      |
      +-----------------------------------+----------------------------------------------------+
      | body_crc                          | Message body verification.                         |
      +-----------------------------------+----------------------------------------------------+
      | store_size                        | Storage size.                                      |
      +-----------------------------------+----------------------------------------------------+
      | property_list                     | Message attribute list.                            |
      |                                   |                                                    |
      |                                   | -  **name**: attribute name.                       |
      |                                   | -  **value**: attribute value.                     |
      +-----------------------------------+----------------------------------------------------+
      | born_host                         | IP address of the host that generates the message. |
      +-----------------------------------+----------------------------------------------------+
      | store_host                        | IP address of the host that stores the message.    |
      +-----------------------------------+----------------------------------------------------+
      | queue_id                          | Queue ID.                                          |
      +-----------------------------------+----------------------------------------------------+
      | queue_offset                      | Offset in the queue.                               |
      +-----------------------------------+----------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0143929918.png
.. |image4| image:: /_static/images/en-us_image_0000001143589128.png
.. |image5| image:: /_static/images/en-us_image_0143929918.png
.. |image6| image:: /_static/images/en-us_image_0000001143589128.png
