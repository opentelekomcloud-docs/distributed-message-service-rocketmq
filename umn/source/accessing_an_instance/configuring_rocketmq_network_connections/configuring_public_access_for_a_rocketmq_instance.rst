:original_name: hrm-ug-033.html

.. _hrm-ug-033:

Configuring Public Access for a RocketMQ Instance
=================================================

To access a RocketMQ instance over a public network, enable public access and configure EIPs for the instance. If you no longer need public access to the instance, disable it.

Notes and Constraints
---------------------

Only IPv4 EIPs can be bound to RocketMQ instances.

Prerequisite
------------

You can change the public access setting only when the RocketMQ instance is in the **Running** state.

Enabling Public Access
----------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. Click |image3| next to **Public Access** in the **Connection** area.

#. Click |image4|, in the **Elastic IP Address** area, select IP addresses as prompted, and click |image5|.

   If no EIP exists in the **Elastic IP Address** drop-down list box, or the EIPs are insufficient, click **Create Elastic IP** to create an EIP on the page that is displayed. After the EIP is created, return to the RocketMQ console, click |image6| next to **Elastic IP Address**, and select the new EIP from the drop-down list.

   After public access is enabled, **Instance Address (Public Network)** and **gRPC Connection Address** will be displayed for a RocketMQ instance.


   .. figure:: /_static/images/en-us_image_0000002338076217.png
      :alt: **Figure 1** Instance Address (Public Network)

      **Figure 1** Instance Address (Public Network)

   After public access is enabled, modify security group rules before attempting to access the RocketMQ instance.

   .. table:: **Table 1** Security group rules

      +-----------+----------+-------+-------------------------------------------------------+---------------------------------------------------------------------+
      | Direction | Protocol | Port  | Source                                                | Description                                                         |
      +===========+==========+=======+=======================================================+=====================================================================+
      | Inbound   | TCP      | 8200  | IP address or IP address group of the RocketMQ client | The port is used for public network access to instances using TCP.  |
      +-----------+----------+-------+-------------------------------------------------------+---------------------------------------------------------------------+
      | Inbound   | TCP      | 8081  |                                                       | The port is used for public network access to instances using gRPC. |
      +-----------+----------+-------+-------------------------------------------------------+---------------------------------------------------------------------+
      | Inbound   | TCP      | 10101 |                                                       | The port is used for public access to service nodes using TCP.      |
      +-----------+----------+-------+-------------------------------------------------------+---------------------------------------------------------------------+

Disabling Public Access
-----------------------

#. Log in to the console.

#. Click |image7| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image8| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. Click |image9| next to **Public Access** in the **Connection** area.

#. Click |image10| and then |image11| to disable public access.

   After public access is disabled, modify security group rules before attempting to access the RocketMQ instance over a private network.

   .. table:: **Table 2** Security group rules

      +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
      | Direction | Protocol | Port  | Source                                                | Description                                                          |
      +===========+==========+=======+=======================================================+======================================================================+
      | Inbound   | TCP      | 8100  | IP address or IP address group of the RocketMQ client | The port is used for private network access to instances using TCP.  |
      +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
      | Inbound   | TCP      | 8080  |                                                       | The port is used for private network access to instances using gRPC. |
      +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+
      | Inbound   | TCP      | 10100 |                                                       | The port is used for private access to service nodes using TCP.      |
      +-----------+----------+-------+-------------------------------------------------------+----------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0000001093972624.png
.. |image4| image:: /_static/images/en-us_image_0000001191767177.png
.. |image5| image:: /_static/images/en-us_image_0000002146696349.png
.. |image6| image:: /_static/images/en-us_image_0000002119729314.png
.. |image7| image:: /_static/images/en-us_image_0143929918.png
.. |image8| image:: /_static/images/en-us_image_0000001143589128.png
.. |image9| image:: /_static/images/en-us_image_0000001093972624.png
.. |image10| image:: /_static/images/en-us_image_0000002231660889.png
.. |image11| image:: /_static/images/en-us_image_0000002146721377.png
