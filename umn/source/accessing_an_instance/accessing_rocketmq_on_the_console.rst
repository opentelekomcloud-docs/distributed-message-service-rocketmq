:original_name: hrm-ug-049.html

.. _hrm-ug-049:

Accessing RocketMQ on the Console
=================================

This section describes how to produce a specified message for a RocketMQ instance to verify service logic.

Prerequisites
-------------

-  A RocketMQ instance is in the **Running** state.
-  A topic has been :ref:`created <hrm-ug-008>` and has the publish permission.

Accessing RocketMQ on the Console to Produce Messages
-----------------------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Topics**.

#. Click **Produce Message** in the row containing the desired topic. The **Produce Message** dialog box is displayed.

#. .. _hrm-ug-049__li0177144134310:

   Enter the message body, key, and tag (**Message Key** and **Message Tag** are optional) and click **OK**.

   When a message "Message sent." is displayed in the upper right corner, the message is sent.

   .. table:: **Table 1** Message production parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                       |
      +===================================+===================================================================================================================================+
      | Message Body                      | Content of the message to be produced.                                                                                            |
      |                                   |                                                                                                                                   |
      |                                   | The value can contain a maximum of 2,000 characters.                                                                              |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Message Key                       | If there are spaces, this will be parsed as multiple keys, and cannot be filtered by **Message Key** in specific message queries. |
      |                                   |                                                                                                                                   |
      |                                   | The value can contain a maximum of 128 characters.                                                                                |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Message Tag                       | Used as message categories in a topic, and used in produced messages.                                                             |
      |                                   |                                                                                                                                   |
      |                                   | The value can contain a maximum of 128 characters.                                                                                |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+

   You can view the sent messages on the **Message Query** page.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
