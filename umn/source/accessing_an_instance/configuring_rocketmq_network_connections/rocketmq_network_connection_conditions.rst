:original_name: hrm-ug-075.html

.. _hrm-ug-075:

RocketMQ Network Connection Conditions
======================================

A client can connect to a RocketMQ instance over a public or private network. Notes before using a private network:

-  By default, a client and a RocketMQ instance are interconnected when they are deployed in a VPC.
-  If they are not, you need to interconnect them because of isolation among VPCs.

:ref:`Table 1 <hrm-ug-075__table870241333211>` lists how a client can connect to a RocketMQ instance.

.. _hrm-ug-075__table870241333211:

.. table:: **Table 1** Connection modes

   +----------------+------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
   | Mode           | How To Do                                                                                                                                      | Reference                                                                                              |
   +================+================================================================================================================================================+========================================================================================================+
   | Public access  | Enable public access on the RocketMQ console and configure elastic IPs (EIPs). The client can connect to the RocketMQ instance through EIPs.   | :ref:`Configuring Public Access for a RocketMQ Instance <hrm-ug-033>`                                  |
   +----------------+------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
   | Private access | A client and a RocketMQ instance are interconnected when they are deployed in a VPC.                                                           | ``-``                                                                                                  |
   +----------------+------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
   |                | When a client and a RocketMQ instance are deployed in different VPCs of the same region, interconnect two VPCs using a VPC peering connection. | `VPC Peering Connection <https://docs.otc.t-systems.com/en-us/usermanual/vpc/vpc_peering_0000.html>`__ |
   +----------------+------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+

Before connecting a client to a RocketMQ instance, allow accesses for the following security groups.

.. note::

   After a security group is created, its default inbound rule allows communication among ECSs within the security group and its default outbound rule allows all outbound traffic. In this case, you can access a RocketMQ instance within a VPC, and do not need to add rules according to :ref:`Table 2 <hrm-ug-075__table161395381402>` or :ref:`Table 3 <hrm-ug-075__table068716651714>`.

.. _hrm-ug-075__table161395381402:

.. table:: **Table 2** Security group rules (RocketMQ 4.8.0)

   +-----------+----------+-------------+-------------------------------------------------------+--------------------------------------------------------------------------+
   | Direction | Protocol | Port        | Source                                                | Description                                                              |
   +===========+==========+=============+=======================================================+==========================================================================+
   | Inbound   | TCP      | 8100        | IP address or IP address group of the RocketMQ client | The port is used for private network access to metadata nodes using TCP. |
   +-----------+----------+-------------+-------------------------------------------------------+--------------------------------------------------------------------------+
   | Inbound   | TCP      | 8200        |                                                       | The port is used for public network access to metadata nodes using TCP.  |
   +-----------+----------+-------------+-------------------------------------------------------+--------------------------------------------------------------------------+
   | Inbound   | TCP      | 10100-10199 |                                                       | The port is used for private access to service nodes using TCP.          |
   +-----------+----------+-------------+-------------------------------------------------------+--------------------------------------------------------------------------+
   | Inbound   | TCP      | 10101-10199 |                                                       | The port is used for public access to service nodes using TCP.           |
   +-----------+----------+-------------+-------------------------------------------------------+--------------------------------------------------------------------------+

.. _hrm-ug-075__table068716651714:

.. table:: **Table 3** Security group rules (RocketMQ 5.x)

   +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
   | Direction | Protocol | Port  | Source                                                | Description                                                          |
   +===========+==========+=======+=======================================================+======================================================================+
   | Inbound   | TCP      | 8100  | IP address or IP address group of the RocketMQ client | The port is used for private network access to instances using TCP.  |
   +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
   | Inbound   | TCP      | 8200  |                                                       | The port is used for public network access to instances using TCP.   |
   +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
   | Inbound   | TCP      | 8080  |                                                       | The port is used for private network access to instances using gRPC. |
   +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
   | Inbound   | TCP      | 8081  |                                                       | The port is used for public network access to instances using gRPC.  |
   +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
   | Inbound   | TCP      | 10100 |                                                       | The port is used for private access to service nodes using TCP.      |
   +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
   | Inbound   | TCP      | 10101 |                                                       | The port is used for public access to service nodes using TCP.       |
   +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
