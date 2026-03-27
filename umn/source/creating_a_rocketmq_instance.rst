:original_name: hrm-ug-002.html

.. _hrm-ug-002:

Creating a RocketMQ Instance
============================

RocketMQ instances are physically isolated and exclusively occupied by each tenant. You can customize specifications and storage space of a RocketMQ instance as required.

Preparing Required Resources
----------------------------

Before creating a RocketMQ instance, prepare the required resources, including a virtual private cloud (VPC), subnet, and security group with proper rules. Each RocketMQ instance is deployed in a VPC and bound to a specific subnet and security group, which provide an isolated virtual network environment and allow you to easily configure and manage security protection policies.

:ref:`Table 1 <hrm-ug-002__table121034152119>` lists the resources required by a RocketMQ instance.

.. _hrm-ug-002__table121034152119:

.. table:: **Table 1** RocketMQ resources

   +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Resource              | Requirement                                                                                                                                                                                                                                                                                                                               | Operations                                                                                                                                                                                                                                   |
   +=======================+===========================================================================================================================================================================================================================================================================================================================================+==============================================================================================================================================================================================================================================+
   | VPC and subnet        | Configure the VPC and subnet for RocketMQ instances as required. You can use the current account's existing VPC and subnet or create new ones.                                                                                                                                                                                            | For details on how to create a VPC and subnet, see . If you need to create and use a new subnet in an existing VPC, see `Creating a Subnet for the VPC <https://docs.otc.t-systems.com/en-us/usermanual/vpc/en-us_topic_0013748726.html>`__. |
   |                       |                                                                                                                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                              |
   |                       | Note the following when creating a VPC and a subnet:                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                              |
   |                       |                                                                                                                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                              |
   |                       | -  The VPC and the RocketMQ instance must be in the same region.                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                              |
   |                       | -  Use the default settings when creating a VPC and subnet.                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                              |
   +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Security group        | Different RocketMQ instances can use the same security group or different security groups.                                                                                                                                                                                                                                                | For details on how to create a security group, see . For details on how to add rules to a security group, see `Adding a Security Group Rule <https://docs.otc.t-systems.com/en-us/usermanual/vpc/en-us_topic_0030969470.html>`__.            |
   |                       |                                                                                                                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                              |
   |                       | To use RocketMQ instances, add the security group rules described in :ref:`Table 2 <hrm-ug-002__table161395381402>`. You can also add other rules as required.                                                                                                                                                                            |                                                                                                                                                                                                                                              |
   |                       |                                                                                                                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                              |
   |                       | After a security group is created, its default inbound rule allows communication among ECSs within the security group and its default outbound rule allows all outbound traffic. In this case, you can access a RocketMQ instance within a VPC, and do not need to add rules according to :ref:`Table 2 <hrm-ug-002__table161395381402>`. |                                                                                                                                                                                                                                              |
   +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | EIP                   | This parameter is required to enable public access.                                                                                                                                                                                                                                                                                       | For details about how to create an EIP, see `Assigning an EIP <https://docs.otc.t-systems.com/en-us/usermanual/eip/eip_0002.html>`__.                                                                                                        |
   |                       |                                                                                                                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                              |
   |                       | Note the following when creating EIPs:                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                              |
   |                       |                                                                                                                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                              |
   |                       | -  The EIPs must be created in the same region as the RocketMQ instance.                                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                              |
   |                       | -  **The RocketMQ console cannot identify IPv6 EIPs.**                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                              |
   +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _hrm-ug-002__table161395381402:

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


Creating a RocketMQ Instance
----------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click **Create RocketMQ Instance** in the upper right corner of the page.

#. Select a **Region**.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Select a **Project**.

   Projects isolate compute, storage, and network resources across geographical regions. For each region, a preset project is available.

#. Select an **AZ**.

   An AZ is a physical region where resources use independent power supply and networks. AZs are physically isolated but interconnected through an internal network.

   Select AZs as prompted based on the instance version.

#. Enter an **Instance Name**.

   You can customize a name that complies with the rules: 4-64 characters; starts with a letter; can contain only letters, digits, hyphens (-), and underscores (_).

#. Select an **Enterprise Project**.

   This parameter is for enterprise users. An enterprise project manages cloud resources. The enterprise project management service unifies cloud resources in projects, and resources and members in a project. The default project is **default**.

#. Configure the following instance parameters:

   a. **Version**: Only 4.8.0 and 5.x are available.

   b. **Architecture**: Retain the default value. **Single-node** and **Cluster** are available in v5.x. **Cluster** is available in v4.8.0.

      -  **Single-node**: There is only one RocketMQ broker. The single-node architecture can only be used for testing.
      -  **Cluster**: There are multiple RocketMQ brokers.

   c. **Broker Flavor/Flavor**: Select the required flavor.

   d. **Brokers**: Select the required number of brokers.

      This parameter is required only for v4.8.0.

   e. **Storage Space per Broker/Storage Space**: Disk type and total storage space of each broker.

      **The disk type is fixed once the instance is created.**

      The disk type can be high I/O, ultra-high I/O, General Purpose SSD, or Extreme SSD. For details about how to select a disk type, see `Disk Types and Performance <https://docs.otc.t-systems.com/en-us/usermanual/evs/en-us_topic_0014580744.html>`__.

#. Configure the instance network parameters.

   a. Select the created VPC and subnet from the **VPC** drop-down list.

      A VPC provides an isolated virtual network for your RocketMQ instances. You can configure and manage the network.

      **After the RocketMQ instance is created, its VPC and subnet cannot be changed.**

   b. Select a security group.

      A security group is a set of rules for accessing a RocketMQ instance.

#. Configure SSL.

   -  SSL: Ciphertext access with high security, but lower performance.
   -  PLAINTEXT: Plaintext access with high performance, but lower security.
   -  PERMISSIVE: Both ciphertext and plaintext access, depending on the client.

   **The SSL setting can be changed after the instance is created.** Select a transmission mode as required.

#. Configure ACL.

   After ACL is enabled, the permissions for each user are exclusive.

#. Click **Advanced Settings** to configure more parameters.

   -  Configure **Public Access**.

      Public access is disabled by default. You can enable or disable it as required. After public access is enabled, configure an IPv4 EIP for the RocketMQ instance.

   -  Specify tags.

      Tags are used to identify cloud resources. When you have many cloud resources of the same type, you can use tags to classify cloud resources by dimension (for example, usage, owner, or environment).

      -  If you have created predefined tags, select a predefined pair of tag key and value. To view or create predefined tags, click **View predefined tags** on the right. You will then be directed to the TMS console.
      -  You can also create new tags by entering **Tag key** and **Tag value**.

      Up to 20 tags can be added to each RocketMQ instance. For details about the requirements on tags, see :ref:`Configuring Tags for a RocketMQ Instance <hrm-ug-058>`.

   -  Enter a description of the instance.

#. Click **Create Now**.

#. Confirm the instance information, and click **Submit**.

#. Return to the instance list and check whether the instance has been created.

   It takes 3 to 15 minutes to create an instance. During this period, the instance status is **Creating**.

   -  If the instance is created successfully, its status changes to **Running**.
   -  If an instance fails to be created, view it in the **Instance Creation Failures** area, and delete it by referring to :ref:`Deleting a RocketMQ Instance <hrm-ug-005>` and then create a new one. If the instance creation fails again, contact customer service.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
