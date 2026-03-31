:original_name: hrm-pd-004.html

.. _hrm-pd-004:

Specifications
==============

DMS for RocketMQ is compatible with open-source RocketMQ 5.x. Their specifications are described as follows.

.. note::

   RocketMQ processes messages, relying on the disk throughput. RocketMQ performance baseline is in scenarios where ultra-high I/O and higher disks are used and disk bandwidth is below its upper limit. For details about the impact of disk types on RocketMQ performance, see :ref:`Does the Disk Type Affect the RocketMQ Instance Performance? <hrm_faq_028>`

DMS for RocketMQ 5.x Basic Edition
----------------------------------

The specifications of a RocketMQ 5.x basic edition instance are defined on six dimensions:

-  ECS flavor: flavor of the ECS used by the instance
-  Disk type: defines the storage space. High I/O, general-purpose SSD, extreme SSD, and ultra-high I/O types are available.
-  Storage space: storage capacity the instance can use
-  TPS: TPS performance of the instance
-  Max. topics: number of topics allowed for the instance
-  Max. consumer groups: number of consumer groups allowed for the instance

:ref:`Table 1 <hrm-pd-004__table9342191210132>` and :ref:`Table 2 <hrm-pd-004__table1045916186574>` list the flavors of DMS for RocketMQ 5.x basic edition. In the following tables, TPS is calculated using 4 KB normal messages. The TPS of sending scheduled, delayed, or transactional messages is that of sending normal messages multiplied by 5. For receiving these messages, do not do the multiplication. For example, the TPS of sending a normal message per second is 1, and TPS of sending a transactional message per second is 5 (1 x 5).

.. _hrm-pd-004__table9342191210132:

.. table:: **Table 1** Instance flavors (DMS for RocketMQ 5.x basic edition single-node)

   +---------------------+--------------------+-----+-------------+----------------------+
   | Flavor              | Storage Space (GB) | TPS | Max. Topics | Max. Consumer Groups |
   +=====================+====================+=====+=============+======================+
   | rocketmq.b1.large.1 | 100-30,000         | 500 | 50          | 500                  |
   +---------------------+--------------------+-----+-------------+----------------------+

.. _hrm-pd-004__table1045916186574:

.. table:: **Table 2** Instance flavors (DMS for RocketMQ 5.x basic edition cluster)

   +----------------------+--------------------+-------+-------------+----------------------+------------------+
   | Flavor               | Storage Space (GB) | TPS   | Max. Topics | Max. Consumer Groups | Max. Connections |
   +======================+====================+=======+=============+======================+==================+
   | rocketmq.b2.large.4  | 200-60,000         | 2,000 | 100         | 1000                 | 4,000            |
   +----------------------+--------------------+-------+-------------+----------------------+------------------+
   | rocketmq.b2.large.8  | 200-60,000         | 4,000 | 100         | 1000                 | 4,000            |
   +----------------------+--------------------+-------+-------------+----------------------+------------------+
   | rocketmq.b2.large.12 | 200-60,000         | 6,000 | 100         | 1000                 | 6,000            |
   +----------------------+--------------------+-------+-------------+----------------------+------------------+
