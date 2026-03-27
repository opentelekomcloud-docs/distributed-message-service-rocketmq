:original_name: hrm-ug-050.html

.. _hrm-ug-050:

Verifying RocketMQ Message Consumption
======================================

Consumption verification is to resend messages to a specified online client to verify that the consumer can receive messages. Consumption verification causes repeated message consumption.

Prerequisites
-------------

-  Consumption can be verified only when an instance is in the **Running** state.
-  Ensure that the client for which consumption is to be verified is online and the consumer has subscribed to the topic whose message is to be resent.


Verifying RocketMQ Message Consumption
--------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Message Query**.

#. Set search criteria on the top of the page.

#. In the row that contains the message to be resent, click **Verify Consumption**. The **Verify Consumption** dialog box is displayed.

#. Set parameters by referring to :ref:`Table 1 <hrm-ug-050__table138829501925>`.

   .. _hrm-ug-050__table138829501925:

   .. table:: **Table 1** Consumption verification parameters

      +-----------+---------------------------------------------------------------------+
      | Parameter | Description                                                         |
      +===========+=====================================================================+
      | Group ID  | Name of the consumer group for which consumption is to be verified. |
      +-----------+---------------------------------------------------------------------+
      | Client ID | ID of the client for which consumption is to be verified.           |
      +-----------+---------------------------------------------------------------------+

#. Click **OK**.

   After the message is successfully resent, "Verified" is displayed on the top of the **Verify Consumption** dialog box. The client should have received the resent message.

   **Consumption verification causes repeated message consumption.**

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
