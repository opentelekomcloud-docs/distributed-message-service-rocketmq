:original_name: hrm-ug-039.html

.. _hrm-ug-039:

Accessing RocketMQ on a Client (Without SSL)
============================================

This section describes how to use TCP to connect to a RocketMQ instance without SSL in CLI mode on Linux.

Setting **SSL** to **PLAINTEXT** or **PERMISSIVE** (plaintext transmission) during instance creation or in the basic instance information disables SSL.

Prerequisites
-------------

-  A RocketMQ instance has been created and you have obtained the connection addresses for intra-VPC access or public network access. For private access, use port 8100. For public access, use port 8200.
-  The network between the client and the RocketMQ instance has been established. For details about network requirements, see :ref:`RocketMQ Network Connection Conditions <hrm-ug-075>`.
-  :ref:`Security group rules <hrm-ug-002__table161395381402>` have been configured.
-  :ref:`A topic has been created <hrm-ug-008>`. The topic name has been obtained and publish and subscribe permissions are granted.
-  `JDK v1.8.111 or later <https://www.oracle.com/java/technologies/downloads/#java8>`__ has been installed on the client server, and related environment variables have been configured.
-  The client server can access the Internet to download the sample software package.

Accessing the Instance with CLI
-------------------------------

#. Log in to the client server.

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

      sh mqadmin sendMessage -n "${Connection addresses}" -t ${Topic name} -p "hello rocketmq"

   Parameter description:

   -  **Connection addresses**: the **Instance Address** for private network access or **Instance Address (Public Network)** for public network access
   -  **Topic name**: name of the topic created for the RocketMQ instance
   -  **hello rocketmq**: the produced message content, can be customized.

   In the following example, **11.xxx.xxx.89:8200;11.xxx.xxx.144:8200** are the metadata connection addresses for public network access to the RocketMQ instance, and **topic-test** is the topic name.

   .. code-block::

      sh mqadmin sendMessage -n "11.xxx.xxx.89:8200;11.xxx.xxx.144:8200" -t topic-test -p "hello rocketmq"

#. Consume normal messages using the sample project.

   .. code-block::

      sh mqadmin consumeMessage -n "${Connection addresses}" -t ${Topic name}

   Parameter description:

   -  **Connection addresses**: the **Instance Address** for private network access or **Instance Address (Public Network)** for public network access
   -  **Topic name**: name of the topic created for the RocketMQ instance
   -  **hello rocketmq**: the produced message content, can be customized.

   In the following example, **11.xxx.xxx.89:8200;11.xxx.xxx.144:8200** are the metadata connection addresses for public network access to the RocketMQ instance, and **topic-test** is the topic name.

   .. code-block::

      sh mqadmin consumeMessage -n "11.xxx.xxx.89:8200;11.xxx.xxx.144:8200" -t topic-test

   To stop consuming messages, press **Ctrl**\ +\ **C** to exit.

#. Create messages with traces using the sample project.

   .. code-block::

      sh mqadmin sendMessage -n "${Connection addresses}" -t ${Topic name} -p "hello rocketmq" -m true

   Parameter description:

   -  **Connection addresses**: the **Instance Address** for private network access or **Instance Address (Public Network)** for public network access
   -  **Topic name**: name of the topic created for the RocketMQ instance
   -  **hello rocketmq**: the produced message content, can be customized.

   In the following example, **11.xxx.xxx.89:8200;11.xxx.xxx.144:8200** are the metadata connection addresses for public network access to the RocketMQ instance, and **topic-test** is the topic name.

   .. code-block::

      sh mqadmin sendMessage -n "11.xxx.xxx.89:8200;11.xxx.xxx.144:8200" -t topic-test -p "hello rocketmq" -m true

#. Retrieve messages and send the message traces using the sample project.

   .. code-block::

      sh mqadmin consumeMessage -n "${Connection addresses}" -t ${Topic name} -m true

   Parameter description:

   -  **Connection addresses**: the **Instance Address** for private network access or **Instance Address (Public Network)** for public network access
   -  **Topic name**: name of the topic created for the RocketMQ instance
   -  **hello rocketmq**: the produced message content, can be customized.

   In the following example, **11.xxx.xxx.89:8200;11.xxx.xxx.144:8200** are the metadata connection addresses for public network access to the RocketMQ instance, and **topic-test** is the topic name.

   .. code-block::

      sh mqadmin consumeMessage -n "11.xxx.xxx.89:8200;11.xxx.xxx.144:8200" -t topic-test -m true

   To stop consuming messages, press **Ctrl**\ +\ **C** to exit.
