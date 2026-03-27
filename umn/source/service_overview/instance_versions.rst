:original_name: hrm_pd_024.html

.. _hrm_pd_024:

Instance Versions
=================

This section compares Distributed Message Service (DMS) for RocketMQ versions and the instance types and architectures supported by each version.

Instance Types and Architectures
--------------------------------

.. table:: **Table 1** Instance types and architectures

   ======= ============ ============
   Version Type         Architecture
   ======= ============ ============
   4.8.0   Professional Cluster
   5.x     Basic        Single-node
   \                    Cluster
   ======= ============ ============

Any fault with a single-node instance may affect service SLA and make services unavailable. However, single-node instances are cost-effective so they are suitable for testing.

V5.x Advantages
---------------

Compared to v4.8.0, v5.x has the following advantages:

-  Advanced architecture

   V5.x comes with stateless proxies so proxy access is no longer a problem. V5.x provides POP consumption, which can reduce consumption accumulation.

-  Easy development

   SDKs in multiple languages that support gRPC protocol are available. APIs are simple and friendly.

-  Flexible cost

   Smaller flavors are available. Elastic scale-up helps reduce costs.

-  Better compatibility

   V5.x is compatible with RocketMQ v4.8.0 SDKs, allowing for seamless upgrade.

Comparing Single-node and Cluster Instances
-------------------------------------------

.. table:: **Table 2** Differences between single-node and cluster instances

   +-----------------------+----------------------------------------------------------------------+-------------------------------------------------+
   | Dimension             | Single-node                                                          | Cluster                                         |
   +=======================+======================================================================+=================================================+
   | Environment           | Development, which has no requirement on performance and reliability | Production, which requires HA and no SPOF       |
   +-----------------------+----------------------------------------------------------------------+-------------------------------------------------+
   | Architecture          | HA is supported by ECS, but cannot be ensured if ECS faults occur.   | Distributed HA supports failover.               |
   +-----------------------+----------------------------------------------------------------------+-------------------------------------------------+
   | Limitation            | -  The storage space can be changed. The flavor cannot be changed.   | -  The storage space and flavor can be changed. |
   |                       | -  Versions cannot changed.                                          | -  Versions cannot changed.                     |
   +-----------------------+----------------------------------------------------------------------+-------------------------------------------------+
