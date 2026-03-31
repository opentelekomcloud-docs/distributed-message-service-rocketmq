:original_name: hrm-ug-018.html

.. _hrm-ug-018:

DMS for RocketMQ Metrics
========================

Introduction
------------

This section describes the metrics that DMS for RocketMQ reports to Cloud Eye. You can view metrics and alarms by using the DMS for RocketMQ console.

Namespace
---------

SYS.DMS

Instance Metrics
----------------

.. table:: **Table 1** Instance metrics

   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------------+------------------------------+
   | Metric ID             | Metric Name          | Description                                                                   | Value Range | Unit   | Conversion Rule | Monitored Object (Dimension) | Monitoring Period (Raw Data) |
   +=======================+======================+===============================================================================+=============+========+=================+==============================+==============================+
   | instance_produce_msg  | Created Messages     | Number of messages received by the instance per minute                        | > 0         | Count  | N/A             | RocketMQ instance            | 1 minute                     |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------------+------------------------------+
   | instance_consume_msg  | Retrieved Messages   | Number of messages retrieved from the instance per minute                     | > 0         | Count  | N/A             | RocketMQ instance            | 1 minute                     |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------------+------------------------------+
   | current_topics        | Topics               | Number of topics in the instance                                              | >= 0        | Count  | N/A             | RocketMQ instance            | 1 minute                     |
   |                       |                      |                                                                               |             |        |                 |                              |                              |
   |                       |                      | .. note::                                                                     |             |        |                 |                              |                              |
   |                       |                      |                                                                               |             |        |                 |                              |                              |
   |                       |                      |    This metric is supported for instances purchased on or after May 16, 2022. |             |        |                 |                              |                              |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------------+------------------------------+
   | current_queues        | Queues               | Number of queues in the instance                                              | >= 0        | Count  | N/A             | RocketMQ instance            | 1 minute                     |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------------+------------------------------+
   | instance_accumulation | Accumulated Messages | Total number of messages accumulated in all consumer groups of the instance   | >= 0        | Count  | N/A             | RocketMQ instance            | 1 minute                     |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------------+------------------------------+

Topic Metrics
-------------

.. table:: **Table 2** Topic metrics

   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------+------------------------------+
   | Metric ID            | Metric Name            | Description                                            | Value Range | Unit    | Conversion Rule | Monitored Object (Dimension) | Monitoring Period (Raw Data) |
   +======================+========================+========================================================+=============+=========+=================+==============================+==============================+
   | topic_produce_msg    | Created Messages       | Number of messages received by the topic per minute    | > 0         | Count   | N/A             | RocketMQ instance queue      | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------+------------------------------+
   | topic_consume_msg    | Retrieved Messages     | Number of messages retrieved from the topic per minute | > 0         | Count   | N/A             | RocketMQ instance queue      | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------+------------------------------+
   | topic_produce_rate   | Message Creation Rate  | Number of messages received by the topic per second    | > 0         | Count/s | N/A             | RocketMQ instance queue      | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------+------------------------------+
   | topic_consume_rate   | Message Retrieval Rate | Number of messages retrieved from the topic per second | > 0         | Count/s | N/A             | RocketMQ instance queue      | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------+------------------------------+
   | topic_bytes_in_rate  | Message Creation       | Message creation traffic of the topic                  | >= 0        | Byte/s  | 1024(IEC)       | RocketMQ instance queue      | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------+------------------------------+
   | topic_bytes_out_rate | Message Retrieval      | Message retrieval traffic of the topic                 | >= 0        | Byte/s  | 1024(IEC)       | RocketMQ instance queue      | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------+------------------------------+

Consumer Group Metrics
----------------------

.. table:: **Table 3** Consumer group metrics

   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+---------------------------------------+------------------------------+
   | Metric ID                | Metric Name            | Description                                                                                                        | Value Range | Unit    | Conversion Rule | Monitored Object (Dimension)          | Monitoring Period (Raw Data) |
   +==========================+========================+====================================================================================================================+=============+=========+=================+=======================================+==============================+
   | group_consume_msg        | Retrieved Messages     | Number of messages retrieved by the consumer group per minute                                                      | > 0         | Count   | N/A             | Consumer group of a RocketMQ instance | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                       |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        |    This metric is available only when **Topic** is set to **All topics** on the **By Consumer Group** tab page.    |             |         |                 |                                       |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+---------------------------------------+------------------------------+
   | group_accumulation       | Available Messages     | Number of messages accumulated in the consumer group                                                               | > 0         | Count   | N/A             | Consumer group of a RocketMQ instance | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        | Unit: count                                                                                                        |             |         |                 |                                       |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                       |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        |    This metric is available only when **Topic** is set to **All topics** on the **By Consumer Group** tab page.    |             |         |                 |                                       |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+---------------------------------------+------------------------------+
   | group_topic_consume_msg  | Retrieved Messages     | Number of messages in the specified topic that are retrieved by the consumer group per minute                      | > 0         | Count   | N/A             | Consumer group of a RocketMQ instance | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                       |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        |    This metric is available only when **Topic** is set to a specified topic on the **By Consumer Group** tab page. |             |         |                 |                                       |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+---------------------------------------+------------------------------+
   | group_topic_consume_rate | Message Retrieval Rate | Number of messages in the specified topic that are retrieved by the consumer group per second                      | > 0         | Count/s | N/A             | Consumer group of a RocketMQ instance | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                       |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        |    This metric is available only when **Topic** is set to a specified topic on the **By Consumer Group** tab page. |             |         |                 |                                       |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+---------------------------------------+------------------------------+
   | group_topic_accumulation | Available Messages     | Number of messages in a specific topic                                                                             | > 0         | Count   | N/A             | Consumer group of a RocketMQ instance | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                       |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                       |                              |
   |                          |                        |    This metric is available only when **Topic** is set to a specified topic on the **By Consumer Group** tab page. |             |         |                 |                                       |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+---------------------------------------+------------------------------+

Dead Letter Queue Metrics
-------------------------

.. table:: **Table 4** Dead letter queue metrics

   +------------------+-----------------------------------+---------------------------------------------+-------------+-------+-----------------+------------------------------------------+------------------------------+
   | Metric ID        | Metric Name                       | Description                                 | Value Range | Unit  | Conversion Rule | Monitored Object (Dimension)             | Monitoring Period (Raw Data) |
   +==================+===================================+=============================================+=============+=======+=================+==========================================+==============================+
   | dlq_accumulation | Messages in the Dead Letter Queue | Number of messages in the dead letter queue | >= 0        | Count | N/A             | Dead letter queue of a RocketMQ instance | 1 minute                     |
   +------------------+-----------------------------------+---------------------------------------------+-------------+-------+-----------------+------------------------------------------+------------------------------+

Dimensions
----------

======================== ===========================================
Key                      Value
======================== ===========================================
reliablemq_instance_id   RocketMQ instance
reliablemq_topics        RocketMQ instance queue
reliablemq_groups        Consumer group of a RocketMQ instance
reliablemq_groups_topics Consumer group of a RocketMQ instance queue
reliablemq_dlq_topics    Dead letter queue of a RocketMQ instance
======================== ===========================================
