:original_name: hrm-ug-038.html

.. _hrm-ug-038:

Modifying RocketMQ Specifications
=================================

After creating a RocketMQ instance, you can increase or decrease its specifications. :ref:`Table 1 <hrm-ug-038__table5120257185816>` lists available modification options. Only one object can be modified at a time.

.. _hrm-ug-038__table5120257185816:

.. table:: **Table 1** Specification modification options

   +-------------------------------+----------+----------------------------------------------------------+
   | Modified Object               | Increase | Decrease                                                 |
   +===============================+==========+==========================================================+
   | Storage space (single-node)   | Y        | x                                                        |
   +-------------------------------+----------+----------------------------------------------------------+
   | Instance flavor (single-node) | x        | x                                                        |
   +-------------------------------+----------+----------------------------------------------------------+
   | Storage space (cluster)       | Y        | x                                                        |
   +-------------------------------+----------+----------------------------------------------------------+
   | Instance flavor (cluster)     | Y        | Y (Only some flavors can be decreased. See the console.) |
   +-------------------------------+----------+----------------------------------------------------------+

Impact
------

Increasing the storage space and instance specifications does not affect services.

Prerequisites
-------------

-  The RocketMQ instance is in the **Running** state.
-  The user to modify instance specifications must have the **DMS FullAccess** permission.

Expanding the Storage Space
---------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Modify the instance specifications in either of the following ways:

   -  Locate the row containing the desired instance, choose **Modify Specifications**.
   -  Click a RocketMQ instance name to go to the instance overview page. In the upper right corner, click **Modify Specifications**.

#. Select **Storage** for **Change By** and enter a storage size.

#. Click **Next**.

#. Confirm the information. If **Billing Mode** is **Yearly/Monthly**, click **Pay Now**. If **Billing Mode** is **Pay-per-use**, click **Submit**.

#. The instance is in the **Changing** state on the RocketMQ instance list page.

   When the instance is in the **Running** state, the expanded available storage space can be viewed in **Used/Available Storage Space**.

   .. note::

      Available storage space = Actual storage space - Storage space for storing logs - Disk formatting loss

      For example, if the storage space is expanded to 700 GB, the storage space for storing logs is 100 GB, and the disk formatting loss is 7 GB, then the available storage space after capacity expansion will be 593 GB.

Increasing an Instance Flavor
-----------------------------

Before scaling the instance, ensure that the subnet segments are allowed in the security group.

#. Log in to the console.

#. Click |image3| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image4| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Modify the instance specifications in either of the following ways:

   -  Locate the row containing the desired instance, choose **Modify Specifications**.
   -  Click a RocketMQ instance name to go to the instance overview page. In the upper right corner, click **Modify Specifications**.

#. Select **Flavor** for **Change By** and select a new instance flavor.

#. Click **Next**.

#. Confirm the information. If **Billing Mode** is **Yearly/Monthly**, click **Pay Now**. If **Billing Mode** is **Pay-per-use**, click **Submit**.

#. The instance is in the **Changing** state on the RocketMQ instance list page.

   When the instance is in the **Running** state, view the new instance flavor in **Flavor**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0143929918.png
.. |image4| image:: /_static/images/en-us_image_0000001143589128.png
