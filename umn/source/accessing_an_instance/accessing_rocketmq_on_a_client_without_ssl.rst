:original_name: hrm-ug-039.html

.. _hrm-ug-039:

Accessing RocketMQ on a Client (Without SSL)
============================================

This document describes how to access a RocketMQ instance with SSL disabled on the Linux CLI. When SSL is disabled, data is transmitted in plaintext between a client and a RocketMQ instance at high performance.

.. _hrm-ug-039__en-us_topic_0143117204_section17830048113810:

Prerequisites
-------------

-  A RocketMQ instance with PLAINTEXT or PERMISSIVE for encryption has been created.

-  The network between the client and the RocketMQ instance has been established. For details about network requirements, see :ref:`RocketMQ Network Connection Conditions <hrm-ug-075>`.

-  A RocketMQ instance has been created and its connection address has been obtained.

   The connection address can be obtained from **Basic Information** > **Connection** on the RocketMQ console.

   -  If the client uses TCP, obtain **Instance Address (Private Network)** or **Instance Address (Public Network)**.
   -  If the client uses gPRC, obtain **gRPC Connection Address** or **gRPC Connection Address (Public Network)**.

-  :ref:`Security group rules <hrm-ug-002__table068716651714>` have been configured.

-  :ref:`A topic has been created <hrm-ug-008>`. The topic name has been obtained and publish and subscribe permissions are granted.

-  `Java Development Kit 1.8.111 or later <https://www.oracle.com/java/technologies/downloads/#java8>`__ has been installed on the client server, and related environment variables have been configured.

-  The client server must be able to access the Internet to download the sample software package.

Accessing the Instance with CLI
-------------------------------

#. Log in to the client server using SSH.

#. Download the **rocketmq-tutorial** software package.

   .. code-block::

      wget https://dms-demos.obs.eu-de.otc.t-systems.com/rocketmq-tutorial.zip

#. Decompress the **rocketmq-tutorial** package.

   .. code-block::

      unzip rocketmq-tutorial.zip

#. (Optional) If ACL is enabled for the RocketMQ instance, authentication is required when you run the **mqadmin** command.

   Switch to the directory where the decompressed software package is stored and add the following content to the **conf/tools.yml** file:

   .. code-block::

      accessKey:*******
      secretKey:*******

   **accessKey** and **secretKey** are the username and secret key set on the **Users** page of the console. For details, see :ref:`Creating a User <hrm-ug-035__section491614421020>`.

#. Go to the **rocketmq-tutorial/bin** directory.

   .. code-block::

      cd rocketmq-tutorial/bin

#. .. _hrm-ug-039__en-us_topic_0143117204_li54957760:

   Produce normal messages using the sample project.

   .. code-block::

      sh mqadmin sendMessage -n "${Connection address}" -t ${Topic name} -p "Message content"

   .. _hrm-ug-039__table2032782610313:

   .. table:: **Table 1** Message production parameters

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Description                                                                                                                                               | Example Value                                                                                                    |
      +=======================+===========================================================================================================================================================+==================================================================================================================+
      | Connection address    | Connection address of the RocketMQ instance, which is obtained from :ref:`Prerequisites <hrm-ug-039__en-us_topic_0143117204_section17830048113810>`.      | 11.\ *xxx.xxx*.89:8200;11.\ *xxx.xxx*.144:8200 (public connection addresses as an example, private port is 8100) |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
      | Topic name            | Name of a topic created in the RocketMQ instance, which is obtained from :ref:`Prerequisites <hrm-ug-039__en-us_topic_0143117204_section17830048113810>`. | topic-test                                                                                                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
      | Message content       | The message content is custom.                                                                                                                            | hello rocketmq                                                                                                   |
      |                       |                                                                                                                                                           |                                                                                                                  |
      |                       | The maximum message size supported by RocketMQ is 4 MB. This limit cannot be modified.                                                                    |                                                                                                                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+

   Run the following command with the values obtained in :ref:`Table 1 <hrm-ug-039__table2032782610313>` to produce a normal message:

   .. code-block::

      sh mqadmin sendMessage -n "11.xxx.xxx.89:8200;11.xxx.xxx.144:8200" -t topic-test -p "hello rocketmq"

   The message is produced when the information in the red box shown in the following figure is displayed.

   |image1|

#. Consume normal messages using the sample project.

   .. code-block::

      sh mqadmin consumeMessage -n "${Connection addresses}" -t ${Topic name}

   Run the following command with the values obtained in :ref:`Table 1 <hrm-ug-039__table2032782610313>` to consume normal messages:

   .. code-block::

      sh mqadmin consumeMessage -n "11.xxx.xxx.89:8200;11.xxx.xxx.144:8200" -t topic-test

   The message is consumed when the information in the red box shown in the following figure is displayed.

   |image2|

   To stop consuming messages, press **Ctrl+C** to exit.

#. Create messages with traces using the sample project.

   .. code-block::

      sh mqadmin sendMessage -n "${Connection addresses}" -t ${Topic name} -p "Message content" -m true

   Run the following command with the values obtained in :ref:`Table 1 <hrm-ug-039__table2032782610313>` to produce messages with traces:

   .. code-block::

      sh mqadmin sendMessage -n "11.xxx.xxx.89:8200;11.xxx.xxx.144:8200" -t topic-test -p "hello rocketmq" -m true

   The message is produced when the information in the red box shown in the following figure is displayed.

   |image3|

#. Retrieve messages and send the message traces using the sample project.

   .. code-block::

      sh mqadmin consumeMessage -n "${Connection addresses}" -t ${Topic name} -m true

   Run the following command with the values obtained in :ref:`Table 1 <hrm-ug-039__table2032782610313>` to consume messages with traces:

   .. code-block::

      sh mqadmin consumeMessage -n "11.xxx.xxx.89:8200;11.xxx.xxx.144:8200" -t topic-test -m true

   The message is consumed when the information in the red box shown in the following figure is displayed.

   |image4|

   To stop consuming messages, press **Ctrl+C** to exit.

.. |image1| image:: /_static/images/en-us_image_0000002371881673.png
.. |image2| image:: /_static/images/en-us_image_0000002337843592.png
.. |image3| image:: /_static/images/en-us_image_0000002338003364.png
.. |image4| image:: /_static/images/en-us_image_0000002371961529.png
