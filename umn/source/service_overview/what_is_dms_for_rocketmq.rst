:original_name: hrm-pd-001.html

.. _hrm-pd-001:

What Is DMS for RocketMQ?
=========================

Distributed Message Service (DMS) for RocketMQ is message-oriented middleware that delivers low latency, high flexibility, high throughput, dynamic expansion, easy management, and abundant messaging functions.

DMS for RocketMQ has the following features:

-  Compatibility with open-source RocketMQ clients.
-  Abundant messaging functions, including ordered message delivery, delayed messages, scheduled messages, message retry, dead letter messages, and transactional messages, which meet diverse needs in e-commerce and finance scenarios.
-  Monitoring and analysis functions, including message tracing, message tracking, trace analysis, dead letter message export, monitoring and alarms, which allow you to monitor your services and keep them up and running.

Product Architecture
--------------------


.. figure:: /_static/images/en-us_image_0000001462827681.png
   :alt: **Figure 1** Product architecture (of a v4.8.0 instance)

   **Figure 1** Product architecture (of a v4.8.0 instance)

Architecture description:

-  Brokers receive and store messages sent by producers or forward messages to consumers. A broker consists of one master and two slave nodes.
-  NameServers receive and store broker metadata.
-  Producers obtain metadata from NameServers and send messages to brokers.
-  Consumers obtain metadata from NameServers and then pull messages from brokers.

Message Types
-------------

DMS for RocketMQ supports four messages types.

-  Normal messages: Messages that do not have any features of delayed messages, ordered messages, or transactional messages.
-  Delayed/Scheduled messages: Messages that are delivered to consumers after a specific period after being sent from producers to DMS for RocketMQ.
-  Ordered messages: Messages that are retrieved in the exact order that they are created.
-  Transactional message: Messages that achieve eventual consistency, delivering distributed transaction processing similar to X/Open XA.

Advanced Features
-----------------

DMS for RocketMQ provides four advanced features.

-  Message filtering: Consumers can tag messages in the subscribed topics to retrieve only the required messages.

-  Message retry: DMS for RocketMQ retries sending messages that fail to be consumed. If the message consumption still fails after the maximum number of retries is reached, the messages are sent to the dead letter queue.

   :ref:`Table 1 <hrm-pd-001__table16984253511>` describes the retry mechanism in DMS for RocketMQ.

   .. _hrm-pd-001__table16984253511:

   .. table:: **Table 1** Message retry mechanism

      +-----------------------+-------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Retrieval Type        | Retry Interval                                                                                        | Maximum Retries                                                                                                                                             |
      +=======================+=======================================================================================================+=============================================================================================================================================================+
      | Ordered retrieval     | The interval is set by the **suspendTimeMillis** parameter.                                           | The maximum number of retries is set by the **setMaxReconsumeTimes** method on the consumer. If this parameter is not set, there will be unlimited retries. |
      |                       |                                                                                                       |                                                                                                                                                             |
      |                       | The default interval is 1000 ms, that is, 1s.                                                         |                                                                                                                                                             |
      +-----------------------+-------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Normal retrieval      | The interval varies by the retry number, as shown in :ref:`Table 2 <hrm-pd-001__table3229119104411>`. | Set during consumer group creation.                                                                                                                         |
      |                       |                                                                                                       |                                                                                                                                                             |
      |                       |                                                                                                       | Value range: 1-16 times                                                                                                                                     |
      +-----------------------+-------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _hrm-pd-001__table3229119104411:

   .. table:: **Table 2** Intervals between retries in normal retrievals

      ========= ======== ========= ========
      Retry No. Interval Retry No. Interval
      ========= ======== ========= ========
      1         10s      9         7 min
      2         30s      10        8 min
      3         1 min    11        9 min
      4         2 min    12        10 min
      5         3 min    13        20 min
      6         4 min    14        30 min
      7         5 min    15        1 h
      8         6 min    16        2 h
      ========= ======== ========= ========

-  Delayed messages: After being sent from producers to DMS for RocketMQ, messages are delivered to consumers only after a **fixed period**. A producer can specify one of the 18 delay levels listed in :ref:`Table 3 <hrm-pd-001__table6746133810237>`.

   .. _hrm-pd-001__table6746133810237:

   .. table:: **Table 3** Delay levels

      =========== ===== =========== ======
      Delay Level Delay Delay Level Delay
      =========== ===== =========== ======
      1           1s    10          6 min
      2           5s    11          7 min
      3           10s   12          8 min
      4           30s   13          9 min
      5           1 min 14          10 min
      6           2 min 15          20 min
      7           3 min 16          30 min
      8           4 min 17          1 h
      9           5 min 18          2 h
      =========== ===== =========== ======

-  Scheduled messages: After being sent from producers to DMS for RocketMQ, messages are delivered to consumers only after a specified time point. In DMS for RocketMQ, you can schedule messages to be delivered at **any time** within one year. You can also cancel scheduled messages.
