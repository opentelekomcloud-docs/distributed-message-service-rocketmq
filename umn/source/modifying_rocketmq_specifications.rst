:original_name: hrm-ug-038.html

.. _hrm-ug-038:

Modifying RocketMQ Specifications
=================================

After creating a RocketMQ 4.8.0 instance, you can increase its specifications. :ref:`Table 1 <hrm-ug-038__table19463154616167>` lists available modification options.

.. _hrm-ug-038__table19463154616167:

.. table:: **Table 1** Specification modification options (RocketMQ 4.8.0)

   =============== ======== ========
   Modified Object Increase Decrease
   =============== ======== ========
   Broker quantity Y        x
   Storage space   Y        x
   Broker flavor   Y        x
   =============== ======== ========

After creating a RocketMQ 5.x instance, you can increase its specifications. :ref:`Table 2 <hrm-ug-038__table78601524172017>` lists available modification options.

.. _hrm-ug-038__table78601524172017:

.. table:: **Table 2** Specification modification options (RocketMQ 5.x)

   ============================= ======== ========
   Modified Object               Increase Decrease
   ============================= ======== ========
   Storage space (single-node)   Y        x
   Instance flavor (single-node) x        x
   Storage space (cluster)       Y        x
   Instance flavor (cluster)     Y        Y
   ============================= ======== ========

Constraints
-----------

-  You can expand the storage space 20 times.
-  When brokers are added, the storage space is proportionally expanded based on the current disk space. For example, assume that the original number of brokers of an instance is 1 and the disk size of each broker is 300 GB. If the broker quantity changes to 2 and the disk size of each broker is still 300 GB, the total disk size becomes 600 GB.
-  **rocketmq.4u8g.cluster.small** does not support broker flavor increase.

Prerequisites
-------------

A RocketMQ instance has been created and is in the **Running** state.

Procedure
---------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Modify the instance specifications in either of the following ways:

   -  Locate the row containing the desired instance, choose **More** > **Modify Specifications**.
   -  Click a RocketMQ instance to go to the instance details page. In the upper right corner, choose **More** > **Modify Specifications**.

#. Configure the broker expansion as required.

   -  RocketMQ 4.8.0: Specify the required storage space, broker quantity, or broker flavor.

      -  Expand the storage space.

         For **Change By**, select **Storage**. For **Storage Space per Broker**, specify a new storage space, and click **Next**. Confirm the configurations and click **Submit**.

         View the new storage space (Storage space per broker x Number of brokers) in the **Used/Available Storage Space (GB)** column in the instance list.

         .. note::

            -  Storage space expansion does not affect services.

            -  Available storage space = Actual storage space - Storage space for storing logs - Disk formatting loss

               For example, if the storage space is expanded to 700 GB, the storage space for storing logs is 100 GB, and the disk formatting loss is 7 GB, then the available storage space after capacity expansion will be 593 GB.

      -  Add brokers.

         For **Change By**, select **Brokers**. Then, enter the number of brokers and click **Next**. Confirm the configurations and click **Submit**.

         View the number of brokers in the **Flavor** column in the instance list.

         -  **Before adding brokers, ensure that the network segments allowed in the security group and the instance ports allowed externally are available. The allowed network segments are the subnet segments of the instance. The allowed port range is 10100-(10100 + 3 x Broker quantity - 1).**
         -  **If public access is enabled and EIPs are configured for the instance, configure EIPs for the new brokers.**

            .. note::

               Adding brokers does not affect the original brokers or services.

      -  Increase the broker flavor.

         For **Change By**, select **Broker Flavor**. Then, select a new flavor and click **Next**. Confirm the configurations and click **Submit**.

         View the broker flavor in the **Flavor** column of the instance list.

         **Increasing the broker flavor will interrupt the instance for about one minute. If the production TPS is high during the change, the change may fail. Increase the broker quantity first if needed.**

   -  RocketMQ 5.x: Specify the required storage space or instance flavor.

      -  Expand the storage space.

         For **Modify By**, select **Storage**. For **Storage**, specify a new storage space, and click **Next**. Confirm the configurations and click **Submit**.

         View the new storage space in the **Used/Available Storage Space (GB)** column in the instance list.

         .. note::

            -  Storage space expansion does not affect services.

            -  Available storage space = Actual storage space - Storage space for storing logs - Disk formatting loss

               For example, if the storage space is expanded to 700 GB, the storage space for storing logs is 20 GB, and the disk formatting loss is 7 GB, then the available storage space after capacity expansion will be 673 GB.

      -  Increase the instance flavor.

         For **Modify By**, select **Flavor**. Then, select a new flavor and click **Next**. Confirm the configurations and click **Submit**.

         View the new flavor in the **Flavor** column of the instance list.

         **Before scaling the instance, ensure that the subnet segments are allowed in the security group.**

         .. note::

            Increasing an instance flavor does not affect services.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
