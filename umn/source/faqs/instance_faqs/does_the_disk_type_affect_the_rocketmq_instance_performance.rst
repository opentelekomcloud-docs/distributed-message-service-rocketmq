:original_name: hrm_faq_028.html

.. _hrm_faq_028:

Does the Disk Type Affect the RocketMQ Instance Performance?
============================================================

About Message Production
------------------------

RocketMQ persists received messages on disks and the message production throughput varies with the disk type. Higher disk throughput is more friendly to performant message production. When the disk performance is used up, disk access latency increases, causing higher message production request latency or even failure.

About Message Consumption
-------------------------

RocketMQ serially flushes messages to disks. A new message is stored in memory first, from which consumers start to consume the latest message.

In other cases, RocketMQ reads history messages from the disk and saves them to memory, that is, cold reads. Many cold reads consume many I/O resources, approaching the disk performance threshold. Message pulling may be slower or fail, causing the consumption rate to decrease.

Avoid using DMS for RocketMQ simultaneously in cold read-sensitive scenarios. For example, resetting the consumer offset of a consumer group in batches or consuming messages from an earlier offset when services are provisioned in batches. In production environments, ultra-high I/o and higher disks are recommended to avoid service exceptions caused by I/O bottlenecks.
