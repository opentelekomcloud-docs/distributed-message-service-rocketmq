:original_name: hrm-pd-004.html

.. _hrm-pd-004:

Specifications
==============

DMS for RocketMQ is compatible with open-source RocketMQ 4.8.0 and 5.x. Their specifications are described as follows.

.. note::

   RocketMQ process messages, relying on the disk throughput. Ultra-high I/O and higher disks satisfy the performance baseline but high I/O ones may not.

DMS for RocketMQ 4.8.0
----------------------

The specifications of a RocketMQ 4.8.0 instance are defined on seven dimensions:

-  ECS flavor: flavor of the ECS used by the instance
-  Number of brokers: scale of the instance
-  Disk type: defines the storage space. High I/O, General Purpose SSD, Extreme SSD, and ultra-high I/O types are available.
-  Storage space: storage capacity available for each broker
-  TPS per broker: TPS performance of each broker
-  Max. topics per broker: number of topics allowed for each broker
-  Max. consumer groups per broker: number of consumer groups allowed for each broker

:ref:`Table 1 <hrm-pd-004__table4797177191712>` lists the flavors of DMS for RocketMQ 4.8.0.

.. note::

   TPS (Transaction per second) indicates the total number of produced and consumed messages per second, that is, the total throughput of message production and consumption per second for a flavor.

.. _hrm-pd-004__table4797177191712:

.. table:: **Table 1** Instance flavors (DMS for RocketMQ 4.8.0)

   +-----------------------------+---------+-------------------------------+----------------+------------------------+---------------------------------+
   | Flavor                      | Brokers | Storage Space (GB per Broker) | TPS per Broker | Max. Topics per Broker | Max. Consumer Groups per Broker |
   +=============================+=========+===============================+================+========================+=================================+
   | rocketmq.4u8g.cluster.small | 1-10    | 300-30,000                    | 15,000         | 2,000                  | 2,000                           |
   +-----------------------------+---------+-------------------------------+----------------+------------------------+---------------------------------+
   | rocketmq.4u8g.cluster       | 1-10    | 300-60,000                    | 20,000         | 4,000                  | 4,000                           |
   +-----------------------------+---------+-------------------------------+----------------+------------------------+---------------------------------+
   | rocketmq.8u16g.cluster      | 1-10    | 300-90,000                    | 25,000         | 8,000                  | 8,000                           |
   +-----------------------------+---------+-------------------------------+----------------+------------------------+---------------------------------+
   | rocketmq.12u24g.cluster     | 1-10    | 300-90,000                    | 28,000         | 12,000                 | 12,000                          |
   +-----------------------------+---------+-------------------------------+----------------+------------------------+---------------------------------+
   | rocketmq.16u32g.cluster     | 1-10    | 300-90,000                    | 30,000         | 16,000                 | 16,000                          |
   +-----------------------------+---------+-------------------------------+----------------+------------------------+---------------------------------+

DMS for RocketMQ 5.x Basic Edition
----------------------------------

The specifications of a RocketMQ 5.x basic edition instance are defined on six dimensions:

-  ECS flavor: flavor of the ECS used by the instance
-  Disk type: defines the storage space. High I/O, General Purpose SSD, Extreme SSD, and ultra-high I/O types are available.
-  Storage space: storage capacity the instance can use
-  TPS: TPS performance of the instance
-  Max. topics: number of topics allowed for the instance
-  Max. consumer groups: number of consumer groups allowed for the instance

:ref:`Table 2 <hrm-pd-004__table9342191210132>` and :ref:`Table 3 <hrm-pd-004__table1045916186574>` list the flavors of DMS for RocketMQ 5.x basic edition. In the following tables, TPS is calculated using 4 KB normal messages. The TPS of sending scheduled, delayed, or transactional messages is that of sending normal messages multiplied by 5. For receiving these messages, do not do the multiplication. For example, the TPS of sending a normal message per second is 1, and TPS of sending a transactional message per second is 5 (1 x 5).

.. _hrm-pd-004__table9342191210132:

.. table:: **Table 2** Instance flavors (DMS for RocketMQ 5.x basic edition single-node)

   +---------------------+--------------------+-----+-------------+----------------------+
   | Flavor              | Storage Space (GB) | TPS | Max. Topics | Max. Consumer Groups |
   +=====================+====================+=====+=============+======================+
   | rocketmq.b1.large.1 | 100-30,000         | 500 | 50          | 500                  |
   +---------------------+--------------------+-----+-------------+----------------------+

.. _hrm-pd-004__table1045916186574:

.. table:: **Table 3** Instance flavors (DMS for RocketMQ 5.x basic edition cluster)

   +----------------------+--------------------+-------+-------------+----------------------+------------------+
   | Flavor               | Storage Space (GB) | TPS   | Max. Topics | Max. Consumer Groups | Max. Connections |
   +======================+====================+=======+=============+======================+==================+
   | rocketmq.b2.large.4  | 200-60,000         | 2,000 | 100         | 1000                 | 4,000            |
   +----------------------+--------------------+-------+-------------+----------------------+------------------+
   | rocketmq.b2.large.8  | 200-60,000         | 4,000 | 100         | 1000                 | 4,000            |
   +----------------------+--------------------+-------+-------------+----------------------+------------------+
   | rocketmq.b2.large.12 | 200-60,000         | 6,000 | 100         | 1000                 | 6,000            |
   +----------------------+--------------------+-------+-------------+----------------------+------------------+
