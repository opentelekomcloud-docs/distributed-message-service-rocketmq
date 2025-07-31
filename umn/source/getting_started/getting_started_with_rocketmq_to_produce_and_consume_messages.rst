:original_name: hrm-qs-001.html

.. _hrm-qs-001:

Getting Started with RocketMQ to Produce and Consume Messages
=============================================================

This document takes the example of creating a RocketMQ instance with SSL enabled and accessing it on a client in the same VPC as the instance over a private network for message production and consumption to get you quickly started with Distributed Message Service (DMS).

Procedure
---------


.. figure:: /_static/images/en-us_image_0000001992837069.png
   :alt: **Figure 1** Procedure for using DMS for RocketMQ

   **Figure 1** Procedure for using DMS for RocketMQ

#. :ref:`Step 1: Preparations <hrm-qs-001__section15630142042613>`

   A RocketMQ instance runs in a VPC. Before creating a RocketMQ instance, ensure that a VPC is available.

#. :ref:`Step 2: Create a RocketMQ Instance <hrm-qs-001__section1776719120428>`

   Enable SSL, disable ACL, and configure the created VPC and subnet, and security group.

#. :ref:`Step 3: Create a Topic <hrm-qs-001__section3360197184417>`

   After an instance is created, create a topic for sending and receiving messages.

#. :ref:`Step 4: Connect to a RocketMQ Instance to Produce and Consume Messages <hrm-qs-001__section91920471455>`

   On the client, connect to the instance and use commands to produce and consume messages.

.. _hrm-qs-001__section15630142042613:

Step 1: Preparations
--------------------

#. Grant RocketMQ instance permissions.

   The RocketMQ administrator permission **DMS FullAccess** is required. For details, see :ref:`Creating an IAM User and Granting DMS for RocketMQ Permissions <hrm-ug-030>`.

#. Create a VPC and subnet.

   .. caution::

      The VPC must be created in the same region as the RocketMQ instance.

   A RocketMQ instance runs in a Virtual Private Cloud (VPC). Before creating an instance, ensure that a VPC is available. For details about how to create a VPC and a subnet, see `Creating a VPC <https://docs.otc.t-systems.com/en-us/usermanual/vpc/en-us_topic_0013935842.html>`__.

#. Create a security group.

   See `Creating a Security Group <https://docs.otc.t-systems.com/en-us/usermanual/vpc/en-us_topic_0013748715.html>`__.

   To connect to RocketMQ instances, add the security group rules described in :ref:`Table 1 <hrm-qs-001__table1385271217300>`.

   .. _hrm-qs-001__table1385271217300:

   .. table:: **Table 1** Security group rules

      +-----------+----------+-------------+-------------------------------------------------------+--------------------------------------------------------------------------+
      | Direction | Protocol | Port        | Source                                                | Description                                                              |
      +===========+==========+=============+=======================================================+==========================================================================+
      | Inbound   | TCP      | 8100        | IP address or IP address range of the RocketMQ client | The port is used for private network access to metadata nodes using TCP. |
      +-----------+----------+-------------+-------------------------------------------------------+--------------------------------------------------------------------------+
      | Inbound   | TCP      | 10100-10199 |                                                       | The port is used for accessing service nodes using TCP.                  |
      +-----------+----------+-------------+-------------------------------------------------------+--------------------------------------------------------------------------+

   .. note::

      After a security group is created, its default inbound rule allows communication among ECSs within the security group and its default outbound rule allows all outbound traffic. In this case, you can access a RocketMQ instance within a VPC, and do not need to add rules according to :ref:`Table 1 <hrm-qs-001__table1385271217300>`.

#. Create an elastic cloud server (ECS) and configure environment variables.

   The following takes a Linux ECS as an example. For more information about how to install JDK and configure the environment variables for a Windows ECS, please search the Internet.

   a. Log in to the console, click |image1| in the upper left corner, click **Elastic Cloud Server** under **Computing**, and then create an ECS.

      For details, see `Creating an ECS <https://docs.otc.t-systems.com/en-us/usermanual/ecs/en-us_topic_0021831611.html>`__. If you already have an available ECS, skip this step.

   b. Log in to an ECS as user **root**.

   c. Install the JDK and configure the environment variables **JAVA_HOME** and **PATH**.

      #. Download the JDK.

         .. note::

            Use Oracle JDK instead of ECS's default JDK (for example, OpenJDK), because ECS's default JDK may not be suitable for the sample project. Obtain Oracle JDK 1.8.111 or later from `Oracle's official website <https://www.oracle.com/java/technologies/downloads/#java8>`__.

      #. Run the following command to decompress the JDK package.

         .. code-block::

            tar -zxvf jdk-8u321-linux-x64.tar.gz

         Change **jdk-8u321-linux-x64.tar.gz** to your JDK version.

      #. Run the following command to edit the environment variable file **.bash_profile**:

         .. code-block::

            vim ~/.bash_profile

      #. Press **i** and add the following content.

         .. code-block::

            export JAVA_HOME=/opt/java/jdk1.8.0_321
            export PATH=$JAVA_HOME/bin:$PATH

         Change **/opt/java/jdk1.8.0_321** to the path where you install JDK.

      #. Press **Esc** to exit the editing mode. Enter the following command and press **Enter** to save and exit the environment variable file:

         .. code-block::

            :wq

      #. Run the following command to make the environment variables take effect:

         .. code-block::

            source .bash_profile

   d. Run the following command to check whether the JDK is successfully installed.

      .. code-block::

         java -version

      If the following information is displayed, the JDK is installed successfully:

      .. code-block::

         java version "1.8.0_321"

   e. Run the following command to download the **rocketmq-tutorial** sample software package.

      **Before downloading the sample software package, ensure that the client server can access the Internet.**

      .. code-block::

         wget https://dms-demos.obs.eu-de.otc.t-systems.com/rocketmq-tutorial.zip

   f. Run the following command to decompress **rocketmq-tutorial**.

      .. code-block::

         unzip rocketmq-tutorial.zip

.. _hrm-qs-001__section1776719120428:

Step 2: Create a RocketMQ Instance
----------------------------------

Before using RocketMQ for message production and consumption, create a RocketMQ instance. The VM resource in the instance store topics.

#. Log in to the DMS console, choose **RocketMQ Instances** in the navigation pane, and click **Create RocketMQ Instance** in the upper right corner.

#. Set the instance information. For details, see :ref:`Table 2 <hrm-qs-001__table146166207210>`.

   .. _hrm-qs-001__table146166207210:

   .. table:: **Table 2** Setting instance information

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                  |
      +===================================+==============================================================================================================================================================================================================+
      | Region                            | For lower network latency and faster access to your resources, select the nearest region.                                                                                                                    |
      |                                   |                                                                                                                                                                                                              |
      |                                   | Select eu-de.                                                                                                                                                                                                |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Project                           | Projects isolate compute, storage, and network resources across geographical regions. For each region, a preset project is available.                                                                        |
      |                                   |                                                                                                                                                                                                              |
      |                                   | Select eu-de (default).                                                                                                                                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | AZ                                | Select one AZ or at least three AZs.                                                                                                                                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Instance Name                     | Enter the instance name, for example, **rocketmq-test**.                                                                                                                                                     |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Enterprise Project                | An enterprise project manages project resources in groups. Enterprise projects are logically isolated. Select "default". This parameter is for enterprise users.                                             |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Version                           | Select an instance version. Select **4.8.0**.                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                              |
      |                                   | Fixed once the instance is created. Use the same version as your client.                                                                                                                                     |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Architecture                      | Select an instance architecture. Select **Cluster** here.                                                                                                                                                    |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Broker Flavor                     | Select an instance flavor. Select **rocketmq.4u8g.cluster** here.                                                                                                                                            |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Brokers                           | Specify the instance broker quantity. Enter **1** here.                                                                                                                                                      |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Storage Space per Broker          | Specify the disk type and storage space per broker for storing RocketMQ data. Select **Ultra-high I/O** and enter **300**. Total storage space of an instance = Storage space per broker x Number of brokers |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Select a VPC and a subnet. Here, select the ones created in :ref:`Step 1: Preparations <hrm-qs-001__section15630142042613>`.                                                                                 |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Security Group                    | Select the security group. Here, select the one created in :ref:`Step 1: Preparations <hrm-qs-001__section15630142042613>`.                                                                                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | SSL                               | Ciphertext access with high security, but lower performance. Select **SSL**.                                                                                                                                 |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ACL                               | Enabling ACL can manage permissions for message production and consumption. Do not enable it here.                                                                                                           |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Advanced settings                 |                                                                                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Public Access                     | EIPs are required to enable public access. Do not enable it here.                                                                                                                                            |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tags                              | Identifiers of the RocketMQ instance. Skip it here.                                                                                                                                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Additional information about the instance. Skip it.                                                                                                                                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Create Now**.

#. Confirm the instance information and submit the request.

#. Return to the instance list and check whether the RocketMQ instance has been created.

   It takes 3 to 15 minutes to create an instance. During this period, the instance status is **Creating**.

   -  If the instance is created successfully, its status changes to **Running**.
   -  delete it. Then create a new one. If the instance creation fails again, contact .

#. After the instance is created, click its name to go to the instance basic information page.

#. .. _hrm-qs-001__li1379314018135:

   Record the instance connection addresses for later use.


   .. figure:: /_static/images/en-us_image_0000002230054021.png
      :alt: **Figure 2** Recording instance connection addresses

      **Figure 2** Recording instance connection addresses

.. _hrm-qs-001__section3360197184417:

Step 3: Create a Topic
----------------------

A topic is the basic unit for sending and receiving messages. After creating a RocketMQ instance, you must manually create topics before creating and retrieving messages.

#. Click a RocketMQ instance to go to the instance basic information page.

#. In the navigation pane, choose **Topics**.

#. Click **Create Topic**.

#. .. _hrm-qs-001__li11652913193216:

   Configure the topic name and other parameters by referring to :ref:`Table 3 <hrm-qs-001__table186364410350>`.

   .. _hrm-qs-001__table186364410350:

   .. table:: **Table 3** Topic parameters

      +-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Description                                                                                                                                                      |
      +=============+==================================================================================================================================================================+
      | Topic Name  | Enter a topic name. Enter **Topic01** here.                                                                                                                      |
      +-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Permission  | Permission of the topic. Select **Publish/Subscribe** here. Producers can publish messages to this topic and consumers can consume the messages from this topic. |
      +-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Brokers     | Associated brokers. Select **broker-0** here and enter **3** queues.                                                                                             |
      +-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description | Additional information about the topic. Skip it.                                                                                                                 |
      +-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+


   .. figure:: /_static/images/en-us_image_0000002232701341.png
      :alt: **Figure 3** Creating a topic

      **Figure 3** Creating a topic

#. Click **OK**.

.. _hrm-qs-001__section91920471455:

Step 4: Connect to a RocketMQ Instance to Produce and Consume Messages
----------------------------------------------------------------------

#. Go to the **rocketmq-tutorial/bin** directory on the ECS.

   .. code-block::

      cd rocketmq-tutorial/bin

#. Produce normal messages by the following commands.

   The following is a command example:

   .. code-block::

      JAVA_OPT=-Dtls.enable=true sh mqadmin sendMessage -n "10.xxx.xxx.89:8100;10.xxx.xxx.144:8100" -t Topic01 -p "hello rocketmq"

   -  **10.xxx.xxx.89:8100;10.xxx.xxx.144:8100**: the connection address of the RocketMQ instance, that is, the connection address in :ref:`7 <hrm-qs-001__li1379314018135>`.
   -  **Topic01**: name of the topic created in :ref:`4 <hrm-qs-001__li11652913193216>` for the RocketMQ instance.
   -  **hello rocketmq**: the produced message content, can be customized.

   |image2|

#. Consume normal messages by the following commands.

   The following is a command example:

   .. code-block::

      JAVA_OPT=-Dtls.enable=true sh mqadmin consumeMessage -n "10.xxx.xxx.89:8100;10.xxx.xxx.144:8100" -t Topic01

   |image3|

   The content of **BODY** is the consumed message content.

   To stop consuming messages, press **Ctrl**\ +\ **C** to exit.

Related Information
-------------------

-  Learn more about :ref:`RocketMQ Concepts <hrm-pd-008>`.
-  In RocketMQ instance creation, SSL can be disabled if ciphertext is not needed in access between the consumer client and the producer client. In this case, to access the RocketMQ instance, see :ref:`Accessing RocketMQ on a Client (Without SSL) <hrm-ug-039>`.
-  If you need multiple users and grant different topic and consumer group permissions for them, enable ACL and configure ACL users so that permissions are isolated among users. For details, see :ref:`Enabling RocketMQ ACL <hrm-ug-070>` and :ref:`Configuring RocketMQ ACL Users <hrm-ug-035>`.
-  To enable public access to RocketMQ instances, see :ref:`Configuring Public Access <hrm-ug-033>`.

.. |image1| image:: /_static/images/en-us_image_0000001956117730.png
.. |image2| image:: /_static/images/en-us_image_0000001956117738.png
.. |image3| image:: /_static/images/en-us_image_0000001992837081.png
