:original_name: hrm_ug_046.html

.. _hrm_ug_046:

Migrating RocketMQ Instance Metadata from Others
================================================

Migrate metadata from others' RocketMQ to DMS for RocketMQ.

You can use one of the following migration methods as required:

-  :ref:`Method 1: Run the mqadmin Command to Export the Source Instance Metadata and Then Create a Migration Task in DMS for RocketMQ <hrm_ug_046__section14542025154919>`: Run the **mqadmin** command to export the source instance metadata and then create a migration task in DMS for RocketMQ.
-  :ref:`Method 2: Export the Source Topics and Consumer Groups and Import Them to DMS for RocketMQ Using Scripts <hrm_ug_046__section73331941155110>`: Export the source topics and consumer groups (when the **mqadmin** command cannot be used to export metadata) and import them to DMS for RocketMQ using scripts.

.. note::

   When metadata is imported to topics and consumer groups, they are created on all brokers. In v4.8.0, the maximum topics that can be imported through migration is the maximum topics per broker. For example, a rocketmq.4u8g.cluster instance has two brokers and the maximum topics per broker is 4000, then at most 4000 instance topics can be imported through migration.

Prerequisites
-------------

-  A RocketMQ instance has been created.

-  A Linux host is available, `JDK v1.8.111 or later <https://www.oracle.com/java/technologies/downloads/#java8>`__ has been installed on the host, and related environment variables have been configured.

-  A network environment is prepared.

   A RocketMQ instance can be accessed within a VPC or over a public network. For public network access, the producer and consumer must have public access permissions. Configure the security group as follows.

   .. table:: **Table 1** Security group rules (RocketMQ 4.8.0)

      +-----------+----------+-------------+-------------------------------------------------------+-------------------------------------------------------------------------+
      | Direction | Protocol | Port        | Source                                                | Description                                                             |
      +===========+==========+=============+=======================================================+=========================================================================+
      | Inbound   | TCP      | 8200        | IP address or IP address group of the RocketMQ client | The port is used for public network access to metadata nodes using TCP. |
      +-----------+----------+-------------+-------------------------------------------------------+-------------------------------------------------------------------------+
      | Inbound   | TCP      | 10101-10199 |                                                       | The port is used for public access to service nodes using TCP.          |
      +-----------+----------+-------------+-------------------------------------------------------+-------------------------------------------------------------------------+

-  The client server can access the Internet to download the RocketMQ software package.

.. _hrm_ug_046__section14542025154919:

Method 1: Run the mqadmin Command to Export the Source Instance Metadata and Then Create a Migration Task in DMS for RocketMQ
-----------------------------------------------------------------------------------------------------------------------------

**Metadata of others', self-hosted, or another DMS for RocketMQ instance**

#. Log in to the prepared Linux host and download the RocketMQ software package.

   .. code-block::

      wget https://archive.apache.org/dist/rocketmq/4.9.8/rocketmq-all-4.9.8-bin-release.zip

#. Decompress the software package.

   .. code-block::

      unzip rocketmq-all-4.9.8-bin-release.zip

#. (Optional) If :ref:`ACL <hrm-ug-070>` is enabled for the RocketMQ instance, authentication is required when you run the **mqadmin** command.

   Switch to the directory where the decompressed software package is stored and add the following content to the **conf/tools.yml** file:

   .. code-block::

      accessKey:*******
      secretKey:*******

   **accessKey** and **secretKey** are the username and secret key set on the **Users** page of the console. For details, see :ref:`Creating a User <hrm-ug-035__section491614421020>`.

#. Go to the directory where the decompressed software package is stored and run the following command to query the cluster name:

   .. code-block::

      sh ./bin/mqadmin clusterList -n {nameserver address and port number}

   For example, if the nameserver address and port number are **192.168.0.65:8100**, run the following command:

   .. code-block::

      sh ./bin/mqadmin clusterList -n 192.168.0.65:8100

#. .. _hrm_ug_046__li101281515205412:

   Run the following command to export metadata:

   -  If SSL is disabled, run the following command:

      .. code-block::

         sh ./bin/mqadmin exportMetadata -n {nameserver address and port number} -c {RocketMQ cluster name} -f {Path for storing the exported metadata file}

      For example, if the nameserver address and port number are **192.168.0.65:8100**, the RocketMQ cluster name is **DmsCluster**, and the path for storing exported metadata files is **/tmp/rocketmq/export**, run the following command:

      .. code-block::

         sh ./bin/mqadmin exportMetadata -n 192.168.0.65:8100 -c DmsCluster -f /tmp/rocketmq/export

   -  If SSL is enabled, run the following command:

      .. code-block::

         JAVA_OPT=-Dtls.enable=true sh ./bin/mqadmin exportMetadata -n {nameserver address and port number} -c {RocketMQ cluster name} -f {path for storing the exported metadata file}

      For example, if the nameserver address and port number are **192.168.0.65:8100**, the RocketMQ cluster name is **DmsCluster**, and the path for storing exported metadata files is **/tmp/rocketmq/export**, run the following command:

      .. code-block::

         JAVA_OPT=-Dtls.enable=true sh ./bin/mqadmin exportMetadata -n 192.168.0.65:8100 -c DmsCluster -f /tmp/rocketmq/export

**Migrate metadata on the console.**

#. .. _hrm_ug_046__li617493110146:

   Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Metadata Migration**.

#. Click **Create Migration Task**.

#. Configure the migration task by referring to :ref:`Table 2 <hrm_ug_046__table1791434413216>`.

   .. _hrm_ug_046__table1791434413216:

   .. table:: **Table 2** Migration task parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                     |
      +===================================+=================================================================================================================================================================================================================================+
      | Task Type                         | Select **From self-built RocketMQ to cloud.**                                                                                                                                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Task Name                         | Unique name of the migration task.                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   | A task name must meet the following requirements:                                                                                                                                                                               |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   | -  Contains 4 to 64 characters.                                                                                                                                                                                                 |
      |                                   | -  Contains only letters, digits, hyphens (-), and underscores (_), and must start with a letter.                                                                                                                               |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Overwrite                         | -  If this option is enabled, configurations in the metadata file with the same name as the uploaded file will be modified.                                                                                                     |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   |    Assume that Topic01 on the source instance has three read queues, and Topic01 on the DMS instance has two read queues. If **Overwrite** is enabled, Topic01 on the DMS instance will have three read queues after migration. |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   | -  If this option is disabled, migration of the metadata file with the same name as the uploaded file will fail.                                                                                                                |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   |    Assume that the source instance has Topic01 and Topic02, and the DMS instance has Topic01 and Topic03. If **Overwrite** is disabled, migration of the source Topic01 will fail.                                              |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Metadata                          | See :ref:`5 <hrm_ug_046__li101281515205412>`.                                                                                                                                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   After the migration is complete, view **Task Status** in the migration task list.

   -  If **Task Status** is **Complete**, all metadata has been successfully migrated.
   -  If **Task Status** is **Failed**, some or all metadata fails to be migrated. Click the migration task name to go to the migration task details page. In the **Migration Result** area, view the name of the topic or consumer group that fails to be migrated, the failure cause, and the solution. After the fault is rectified, perform the following steps.

#. Migrate the production service to the RocketMQ instance.

   Change the metadata connection address on the production client to the metadata connection address of the RocketMQ instance and then restart the production service. New messages will be sent to the RocketMQ instance.

#. .. _hrm_ug_046__li182171057291:

   Migrate the consumption service to the RocketMQ instance.

   After all messages in the consumer group are consumed, change the metadata connection address of the consumer client to the metadata connection address of the RocketMQ instance. New messages will be consumed from the RocketMQ instance.

#. If there are multiple source RocketMQ instances, migrate services from them one by one by referring to :ref:`1 <hrm_ug_046__li617493110146>` to :ref:`10 <hrm_ug_046__li182171057291>`.

.. _hrm_ug_046__section73331941155110:

Method 2: Export the Source Topics and Consumer Groups and Import Them to DMS for RocketMQ Using Scripts
--------------------------------------------------------------------------------------------------------

**Metadata of others', self-hosted, or another DMS for RocketMQ instance**

#. Log in to the console of another vendor and export the lists of source topics and consumer groups.

#. Create the **topics.txt** and **groups.txt** files and add the source topic list and consumer group list to the files respectively. Each line contains a topic or consumer group name. For example:

   .. code-block::

      topic-01
      topic-02
      ...
      topic-n

   .. caution::

      The **groups.txt** file cannot contain blank lines (for example, a newline character at the end of a consumer group name). Otherwise, consumer groups with empty names will be created when the lists are imported to the RocketMQ instance.

**Import the source topics and consumer groups to DMS for RocketMQ using the following script:**

#. Log in to the prepared Linux host and download the RocketMQ software package.

   .. code-block::

      wget https://archive.apache.org/dist/rocketmq/4.9.8/rocketmq-all-4.9.8-bin-release.zip

#. Decompress the software package.

   .. code-block::

      unzip rocketmq-all-4.9.8-bin-release.zip

#. (Optional) If :ref:`ACL <hrm-ug-070>` is enabled for the RocketMQ instance, authentication is required when you run the **mqadmin** command.

   Switch to the directory where the decompressed software package is stored and add the following content to the **conf/tools.yml** file:

   .. code-block::

      accessKey:*******
      secretKey:*******

   **accessKey** and **secretKey** are the username and secret key set on the **Users** page of the console.

#. Go to the **bin** directory of the decompressed software package and upload **topics.txt** and **groups.txt** to this directory.

#. Run the following script to import the source topics and consumer groups to DMS for RocketMQ:

   .. code-block::

      #!/bin/bash

      # Read groups from groups.txt file
      groups=()
      while read -r group; do
        groups+=("$group")
      done < "groups.txt"

      # Read topics from topic.txt file
      topics=()
      while read -r topic; do
        topics+=("$topic")
      done < "topics.txt"

      # Add topics
      for topic in "${topics[@]}"; do
        echo "Adding topic: $topic"
        sh mqadmin updateTopic -n <namesrvIp:8100> -c DmsCluster -t "$topic"
      done

      # Add consumer groups
      for group in "${groups[@]}"; do
        echo "Adding consumer group: $group"
        sh mqadmin updateSubGroup -n <namesrvIp:8100> -c DmsCluster -g "$group"
      done

   **namesrvIp:8100** indicates the address of the RocketMQ instance.

#. Log in to the console.

#. Click |image3| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image4| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. In the navigation pane, choose **Metadata Migration**.

#. Click the task name to go to the task details page. **Migration Result** shows whether the topic and consumer group list are imported.

#. Migrate the production service to the RocketMQ instance.

   Change the metadata connection address on the production client to the metadata connection address of the RocketMQ instance and then restart the production service. New messages will be sent to the RocketMQ instance.

#. Migrate the consumption service to the RocketMQ instance.

   After all messages in the consumer group are consumed, change the metadata connection address of the consumer client to the metadata connection address of the RocketMQ instance. New messages will be consumed from the RocketMQ instance.

#. If there are multiple source RocketMQ instances, migrate services from them one by one by referring to :ref:`1 <hrm_ug_046__li617493110146>` to :ref:`10 <hrm_ug_046__li182171057291>`.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0143929918.png
.. |image4| image:: /_static/images/en-us_image_0000001143589128.png
