:original_name: hrm-ug-061.html

.. _hrm-ug-061:

Configuring SSL of a RocketMQ Instance
======================================

Scenario
--------

You can access a RocketMQ instance in plaintext or ciphertext. This section describes how to change the access mode on the console.

RocketMQ instances support the following access modes:

-  SSL: Ciphertext access with high security, but lower performance.
-  PLAINTEXT: Plaintext access with high performance, but lower security.
-  PERMISSIVE: Both ciphertext and plaintext access, depending on the client.

Operation Impact
----------------

:ref:`Table 1 <hrm-ug-061__table5701125211560>` lists the impact of changing the access mode.

**PERMISSIVE** is unavailable for some existing RocketMQ instances. For details, see the console.

.. _hrm-ug-061__table5701125211560:

.. table:: **Table 1** Impact of changing the access mode

   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Server Access Mode Change         | Impact                                                                                                                                                                                                        |
   +===================================+===============================================================================================================================================================================================================+
   | PLAINTEXT > SSL                   | -  Existing instances will restart and services will be interrupted. Change the access mode on the client.                                                                                                    |
   |                                   | -  New instances will not be restarted but services will be interrupted. Change the access mode on the client.                                                                                                |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | SSL > PLAINTEXT                   |                                                                                                                                                                                                               |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | PLAINTEXT > PERMISSIVE            | Instances will not be restarted and services will not be interrupted.                                                                                                                                         |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | SSL > PERMISSIVE                  |                                                                                                                                                                                                               |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | PERMISSIVE > PLAINTEXT            | -  If data is transmitted in plaintext on the client, instances will not be restarted and services will not be interrupted after the access mode is changed on the server.                                    |
   |                                   | -  If data is transmitted in ciphertext on the client, instances will not be restarted but services will be interrupted after the access mode is changed on the server. Change the access mode on the client. |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | PERMISSIVE > SSL                  | -  If data is transmitted in ciphertext on the client, instances will not be restarted and services will not be interrupted after the access mode is changed on the server.                                   |
   |                                   | -  If data is transmitted in plaintext on the client, instances will not be restarted but services will be interrupted after the access mode is changed on the server. Change the access mode on the client.  |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Prerequisite
------------

You can change the access mode of a RocketMQ instance only when the instance is in the **Running** state.

Procedure
---------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. In the **Connection** area, specify **SSL** option. The **Confirm** dialog box is displayed.

#. Click **OK**. The **Background Tasks** page is displayed.

   If the SSL change task is in the **Successful** state, the instance access mode is changed successfully.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
