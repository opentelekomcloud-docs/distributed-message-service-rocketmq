:original_name: hrm-ug-027.html

.. _hrm-ug-027:

Viewing RocketMQ Messages
=========================

RocketMQ messages can be queried by topic, message ID, or message key. You can check whether a message is sent and consumed, whether the message content is correct, and track the message using **Message Query**.

How to Query
------------

:ref:`Table 1 <hrm-ug-027__table9110996812>` compares three modes of query.

.. _hrm-ug-027__table9110996812:

.. table:: **Table 1** Message query modes

   +-----------------+-----------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Search By       | Search With           | Search In       | Description                                                                                                                                                                           |
   +=================+=======================+=================+=======================================================================================================================================================================================+
   | Topic           | Topic and time range  | Range           | Based on a topic and time range, you can obtain all the messages meeting the query criteria in batches. Due to the large number of messages, matching is more difficult.              |
   +-----------------+-----------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Message ID      | Topic and message ID  | Exact mode      | Based on a topic and message ID, you can accurately locate a message to obtain its attributes.                                                                                        |
   +-----------------+-----------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Message key     | Topic and message key | Fuzzy mode      | The latest 64 messages that contain specific keys can be queried by topic and message key.                                                                                            |
   |                 |                       |                 |                                                                                                                                                                                       |
   |                 |                       |                 | A message producer is advised to set a unique key for each message. This ensures that the number of messages with the same key are within 64. Otherwise, some messages may be missed. |
   +-----------------+-----------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Message Deletion Mechanism
--------------------------

Regardless of whether they have been consumed, RocketMQ messages are retained for 48 hours and the upper limit is 720 hours by default. For details about how to modify the retention period, see :ref:`Changing RocketMQ Message Retention Period <hrm-ug-059>`. RocketMQ messages are stored in CommitLog files. Each CommitLog file is 1 GB. When a CommitLog file is full, a new CommitLog file is generated. Message deletion in RocketMQ means to delete the CommitLog files, instead of individual messages. CommitLog files are written in sequence. A CommitLog file expires when the last message written in it expires. CommitLog files are deleted in the following scenarios:

-  Expired files are cleared at 04:00 every day. Earlier instances that do not have a time zone are cleared at 12:00 every day.
-  Expired files are deleted immediately when the disk usage reaches 70% (for v4.8.0) or 75% (for v5.x).
-  The earliest files are deleted, regardless of whether they have expired, when the disk usage reaches 85%.

Prerequisites
-------------

-  A RocketMQ instance and topics have been created.

-  To query messages by message ID, you need the name of the topic to which the message belongs and the message ID.

   Message ID is the **MsgId** returned after the message is produced, for example, the content returned in :ref:`6 <hrm-ug-039__en-us_topic_0143117204_li54957760>`. Message IDs can be recorded in topic queries.

-  To query messages by message key, you need the name of the topic to which the message belongs and the message key.

   Message Key is the message key configured in :ref:`7 <hrm-ug-049__li0177144134310>`. Message keys can be recorded in topic queries.

Querying the Message Content
----------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Message Query**.

#. Query messages in either of the following ways:

   -  By topic: Select the topic to be queried from the **Topic** drop-down list and the queue to the queried from the **Queue** drop-down list (only for RocketMQ 4.8.0). For **Stored**, select a time period.
   -  By message ID: Select the name of the topic to be queried from the **Topic** drop-down list, enter the ID of the message to be queried, and click **Search**.
   -  By message key: Select the name of the topic to be queried from the **Topic** drop-down list, enter the key of the message to be queried, and click **Search**.

#. In the row that contains the desired message, click **View Details** to view the message content.

   The message details include the message size, message creation time, and message content.

   -  If the message body is greater than 4096 bytes, some content may not be displayed on the console. In this case, click **Download** to view the message body in the downloaded JSON file.
   -  Click **Copy** to copy the message content.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
