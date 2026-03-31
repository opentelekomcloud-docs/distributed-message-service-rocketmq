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

   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------+------------------------------+
   | Metric ID             | Metric Name          | Description                                                                   | Value Range | Unit   | Conversion Rule | Dimension              | Monitoring Period (Raw Data) |
   +=======================+======================+===============================================================================+=============+========+=================+========================+==============================+
   | instance_produce_msg  | Created Messages     | Number of messages received by the instance per minute                        | > 0         | Count  | N/A             | reliablemq_instance_id | 1 minute                     |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------+------------------------------+
   | instance_consume_msg  | Retrieved Messages   | Number of messages retrieved from the instance per minute                     | > 0         | Count  | N/A             | reliablemq_instance_id | 1 minute                     |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------+------------------------------+
   | current_topics        | Topics               | Number of topics in the instance                                              | >= 0        | Count  | N/A             | reliablemq_instance_id | 1 minute                     |
   |                       |                      |                                                                               |             |        |                 |                        |                              |
   |                       |                      | .. note::                                                                     |             |        |                 |                        |                              |
   |                       |                      |                                                                               |             |        |                 |                        |                              |
   |                       |                      |    This metric is supported for instances purchased on or after May 16, 2022. |             |        |                 |                        |                              |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------+------------------------------+
   | current_queues        | Queues               | Number of queues in the instance                                              | >= 0        | Count  | N/A             | reliablemq_instance_id | 1 minute                     |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------+------------------------------+
   | instance_accumulation | Accumulated Messages | Total number of messages accumulated in all consumer groups of the instance   | >= 0        | Count  | N/A             | reliablemq_instance_id | 1 minute                     |
   +-----------------------+----------------------+-------------------------------------------------------------------------------+-------------+--------+-----------------+------------------------+------------------------------+

Topic Metrics
-------------

.. table:: **Table 2** Topic metrics

   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------------------+------------------------------+
   | Metric ID            | Metric Name            | Description                                            | Value Range | Unit    | Conversion Rule | Dimension                                | Monitoring Period (Raw Data) |
   +======================+========================+========================================================+=============+=========+=================+==========================================+==============================+
   | topic_produce_msg    | Created Messages       | Number of messages received by the topic per minute    | > 0         | Count   | N/A             | reliablemq_instance_id,reliablemq_topics | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------------------+------------------------------+
   | topic_consume_msg    | Retrieved Messages     | Number of messages retrieved from the topic per minute | > 0         | Count   | N/A             | reliablemq_instance_id,reliablemq_topics | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------------------+------------------------------+
   | topic_produce_rate   | Message Creation Rate  | Number of messages received by the topic per second    | > 0         | Count/s | N/A             | reliablemq_instance_id,reliablemq_topics | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------------------+------------------------------+
   | topic_consume_rate   | Message Retrieval Rate | Number of messages retrieved from the topic per second | > 0         | Count/s | N/A             | reliablemq_instance_id,reliablemq_topics | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------------------+------------------------------+
   | topic_bytes_in_rate  | Message Creation       | Message creation traffic of the topic                  | >= 0        | Byte/s  | 1024(IEC)       | reliablemq_instance_id,reliablemq_topics | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------------------+------------------------------+
   | topic_bytes_out_rate | Message Retrieval      | Message retrieval traffic of the topic                 | >= 0        | Byte/s  | 1024(IEC)       | reliablemq_instance_id,reliablemq_topics | 1 minute                     |
   +----------------------+------------------------+--------------------------------------------------------+-------------+---------+-----------------+------------------------------------------+------------------------------+

Consumer Group Metrics
----------------------

.. table:: **Table 3** Consumer group metrics

   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+-------------------------------------------------------------------+------------------------------+
   | Metric ID                | Metric Name            | Description                                                                                                        | Value Range | Unit    | Conversion Rule | Dimension                                                         | Monitoring Period (Raw Data) |
   +==========================+========================+====================================================================================================================+=============+=========+=================+===================================================================+==============================+
   | group_consume_msg        | Retrieved Messages     | Number of messages retrieved by the consumer group per minute                                                      | > 0         | Count   | N/A             | reliablemq_instance_id,reliablemq_groups                          | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                                                   |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        |    This metric is available only when **Topic** is set to **All topics** on the **By Consumer Group** tab page.    |             |         |                 |                                                                   |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+-------------------------------------------------------------------+------------------------------+
   | group_accumulation       | Available Messages     | Number of messages accumulated in the consumer group                                                               | > 0         | Count   | N/A             | reliablemq_instance_id,reliablemq_groups                          | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        | Unit: count                                                                                                        |             |         |                 |                                                                   |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                                                   |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        |    This metric is available only when **Topic** is set to **All topics** on the **By Consumer Group** tab page.    |             |         |                 |                                                                   |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+-------------------------------------------------------------------+------------------------------+
   | group_topic_consume_msg  | Retrieved Messages     | Number of messages in the specified topic that are retrieved by the consumer group per minute                      | > 0         | Count   | N/A             | reliablemq_instance_id,reliablemq_groups,reliablemq_groups_topics | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                                                   |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        |    This metric is available only when **Topic** is set to a specified topic on the **By Consumer Group** tab page. |             |         |                 |                                                                   |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+-------------------------------------------------------------------+------------------------------+
   | group_topic_consume_rate | Message Retrieval Rate | Number of messages in the specified topic that are retrieved by the consumer group per second                      | > 0         | Count/s | N/A             | reliablemq_instance_id,reliablemq_groups,reliablemq_groups_topics | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                                                   |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        |    This metric is available only when **Topic** is set to a specified topic on the **By Consumer Group** tab page. |             |         |                 |                                                                   |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+-------------------------------------------------------------------+------------------------------+
   | group_topic_accumulation | Available Messages     | Number of messages in a specific topic                                                                             | > 0         | Count   | N/A             | reliablemq_instance_id,reliablemq_groups,reliablemq_groups_topics | 1 minute                     |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        | .. note::                                                                                                          |             |         |                 |                                                                   |                              |
   |                          |                        |                                                                                                                    |             |         |                 |                                                                   |                              |
   |                          |                        |    This metric is available only when **Topic** is set to a specified topic on the **By Consumer Group** tab page. |             |         |                 |                                                                   |                              |
   +--------------------------+------------------------+--------------------------------------------------------------------------------------------------------------------+-------------+---------+-----------------+-------------------------------------------------------------------+------------------------------+

Dead Letter Queue Metrics
-------------------------

.. table:: **Table 4** Dead letter queue metrics

   +------------------+-----------------------------------+---------------------------------------------+-------------+-------+-----------------+----------------------------------------------+------------------------------+
   | Metric ID        | Metric Name                       | Description                                 | Value Range | Unit  | Conversion Rule | Monitored Object (Dimension)                 | Monitoring Period (Raw Data) |
   +==================+===================================+=============================================+=============+=======+=================+==============================================+==============================+
   | dlq_accumulation | Messages in the Dead Letter Queue | Number of messages in the dead letter queue | >= 0        | Count | N/A             | reliablemq_instance_id,reliablemq_dlq_topics | 1 minute                     |
   +------------------+-----------------------------------+---------------------------------------------+-------------+-------+-----------------+----------------------------------------------+------------------------------+

If a monitored object has multiple dimensions, the dimensional level of specific metrics is required when you use APIs to query the metrics.

For example, to query the number of accumulated messages (group_accumulation) of a consumer group, its dimension is "reliablemq_instance_id,reliablemq_groups", indicating that reliablemq_instance_id is numbered 0 and reliablemq_groups is numbered 1.

-  To query a single metric by calling the API, the reliablemq_groups dimension is used as follows:

   .. code-block::

      dim.0=reliablemq_instance_id,6a0df74a-fxxx-497bfdda6c8e&dim.1=reliablemq_groups,10

   **6a0df74a-fxxx-497bfdda6c8e** and **10** are the dimension values of reliablemq_instance_id and reliablemq_groups. For details about how to obtain them, see the guide in the :ref:`Dimension <hrm-ug-018__section710181216219>` table.

-  To batch query metrics by calling the API, the reliablemq_groups dimension is used as follows:

   .. code-block::

      "dimensions": [
                       {
                           "name": "reliablemq_instance_id",
                           "value": "6a0df74a-fxxx-497bfdda6c8e"
                       },
                       {
                           "name": "reliablemq_groups",
                           "value": "10"
                       }
                   ]

   **6a0df74a-fxxx-497bfdda6c8e** and **10** are the dimension values of reliablemq_instance_id and reliablemq_groups. For details about how to obtain them, see the guide in the :ref:`Dimension <hrm-ug-018__section710181216219>` table.

.. _hrm-ug-018__section710181216219:

Dimensions
----------

+--------------------------+---------------------------------------------------------------------------------------+
| Key                      | Value                                                                                 |
+==========================+=======================================================================================+
| reliablemq_instance_id   | RocketMQ instance ID, for example, **6a0df74a-fxxx-497bfdda6c8e**.                    |
+--------------------------+---------------------------------------------------------------------------------------+
| reliablemq_topics        | Topic name, for example, **topic-01**.                                                |
+--------------------------+---------------------------------------------------------------------------------------+
| reliablemq_groups        | RocketMQ instance consumer group, for example, **group-01**.                          |
+--------------------------+---------------------------------------------------------------------------------------+
| reliablemq_groups_topics | Name of the topic consumed, for example, **topic-01**.                                |
+--------------------------+---------------------------------------------------------------------------------------+
| reliablemq_dlq_topics    | Name of the dead letter queue of the RocketMQ instance, for example, **DLQ_group-1**. |
+--------------------------+---------------------------------------------------------------------------------------+
