:original_name: hrm-ug-055.html

.. _hrm-ug-055:

Restarting Brokers of a RocketMQ Instance
=========================================

Restart one or more brokers of a RocketMQ instance at a time on the DMS for RocketMQ console.

**How do I know which broker is the master?**

Each broker has one master node and two standby nodes. For example, to purchase one broker, two brokers will be created. Three brokers are deployed in raft mode with broker IDs 1, 2, and 3. When one broker becomes the master, its broker ID is 0. In this case, the broker whose ID is 0 is the master one.


.. figure:: /_static/images/en-us_image_0000001882195002.png
   :alt: **Figure 1** Restarting brokers

   **Figure 1** Restarting brokers

Notes and Constraints
---------------------

Available only for RocketMQ 4.8.0 and not for 5.x.

During the restart, client requests for message consumption and production will be rejected for up to 30s. Restart brokers during off-peak hours. Restarting slave brokers does not affect services.

Prerequisite
------------

The RocketMQ instance must be running.

Procedure
---------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. In the row containing the desired RocketMQ instance, choose **Restart Broker**.

#. Select the brokers to be restarted and click **Yes**.

   It takes 3 to 15 minutes to restart the brokers.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
