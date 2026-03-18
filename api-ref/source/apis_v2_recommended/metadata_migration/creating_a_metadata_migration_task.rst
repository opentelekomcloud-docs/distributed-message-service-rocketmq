:original_name: CreateRocketMqMigrationTask.html

.. _CreateRocketMqMigrationTask:

Creating a Metadata Migration Task
==================================

Function
--------

This API is used to create a metadata migration task.

URI
---

POST /v2/{project_id}/instances/{instance_id}/metadata

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                      |
   +=================+=================+=================+==================================================================================================================================+
   | project_id      | Yes             | String          | **Definition**                                                                                                                   |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | Project ID. For details about how to obtain it, see :ref:`Obtaining a Project ID <hrm-api-0011>`.                                |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | **Constraints**                                                                                                                  |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                              |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | **Range**                                                                                                                        |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                              |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | **Default Value**                                                                                                                |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------+
   | instance_id     | Yes             | String          | **Definition**                                                                                                                   |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | Instance ID. You can call the API for querying all instances to obtain the instance ID. The instance ID is in the response body. |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | **Constraints**                                                                                                                  |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                              |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | **Range**                                                                                                                        |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                              |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | **Default Value**                                                                                                                |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                      |
   +=================+=================+=================+==================================================================================================================================================================================+
   | overwrite       | Yes             | String          | **Definition**                                                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **true**: Configurations in the metadata file with the same name as the uploaded file will be overwritten. **false**: An error is reported when a topic or group already exists. |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Constraints**                                                                                                                                                                  |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Range**                                                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Default Value**                                                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name            | Yes             | String          | **Definition**                                                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | Migration task name. For details about the naming rules, see the API for creating an instance.                                                                                   |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Constraints**                                                                                                                                                                  |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Range**                                                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Default Value**                                                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | type            | Yes             | String          | **Definition**                                                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | Migration task type. The value can be **rocketmq** or **rabbitToRocket**.                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Constraints**                                                                                                                                                                  |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Range**                                                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **Default Value**                                                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | N/A                                                                                                                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request body parameters

   +--------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                | Mandatory       | Type                                                                                                                              | Description                                                                                                                                                                                                                     |
   +==========================+=================+===================================================================================================================================+=================================================================================================================================================================================================================================+
   | topic_config_table       | No              | Map<String,\ :ref:`MigrationRocketMqTopicConfig <createrocketmqmigrationtask__request_migrationrocketmqtopicconfig>`>             | **Definition**                                                                                                                                                                                                                  |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | RocketMQ instance topic metadata. The topic name is the key and the topic configuration is the value. This parameter is mandatory for **rocketmq** migration tasks (from self-built RocketMQ instances to DMS for RocketMQ).    |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Constraints**                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Range**                                                                                                                                                                                                                       |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Default Value**                                                                                                                                                                                                               |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   +--------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | subscription_group_table | No              | Map<String,\ :ref:`MigrationRocketMqSubscriptionGroup <createrocketmqmigrationtask__request_migrationrocketmqsubscriptiongroup>`> | **Definition**                                                                                                                                                                                                                  |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | RocketMQ consumer group metadata. The consumer group name is the key and the configuration is the value. This parameter is mandatory for **rocketmq** migration tasks (from self-built RocketMQ instances to DMS for RocketMQ). |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Constraints**                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Range**                                                                                                                                                                                                                       |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Default Value**                                                                                                                                                                                                               |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   +--------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vhosts                   | No              | Array of :ref:`MigrationRabbitVhostMetadata <createrocketmqmigrationtask__request_migrationrabbitvhostmetadata>` objects          | **Definition**                                                                                                                                                                                                                  |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | RabbitMQ virtual host metadata list. This parameter is mandatory for **rabbitToRocket** migration tasks (from self-built RabbitMQ instances to DMS for RocketMQ).                                                               |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Constraints**                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Range**                                                                                                                                                                                                                       |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Default Value**                                                                                                                                                                                                               |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   +--------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | queues                   | No              | Array of :ref:`MigrationRabbitQueueMetadata <createrocketmqmigrationtask__request_migrationrabbitqueuemetadata>` objects          | **Definition**                                                                                                                                                                                                                  |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | RabbitMQ queue metadata list. This parameter is mandatory for **rabbitToRocket** migration tasks (from self-built RabbitMQ instances to DMS for RocketMQ).                                                                      |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Constraints**                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Range**                                                                                                                                                                                                                       |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Default Value**                                                                                                                                                                                                               |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   +--------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | exchanges                | No              | Array of :ref:`MigrationRabbitExchangeMetadata <createrocketmqmigrationtask__request_migrationrabbitexchangemetadata>` objects    | **Definition**                                                                                                                                                                                                                  |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | RabbitMQ exchange metadata list. This parameter is mandatory for **rabbitToRocket** migration tasks (from self-built RabbitMQ instances to DMS for RocketMQ).                                                                   |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Constraints**                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Range**                                                                                                                                                                                                                       |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Default Value**                                                                                                                                                                                                               |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   +--------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | bindings                 | No              | Array of :ref:`MigrationRabbitBindingMetadata <createrocketmqmigrationtask__request_migrationrabbitbindingmetadata>` objects      | **Definition**                                                                                                                                                                                                                  |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | RabbitMQ binding metadata list. This parameter is mandatory for **rabbitToRocket** migration tasks (from self-built RabbitMQ instances to DMS for RocketMQ).                                                                    |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Constraints**                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Range**                                                                                                                                                                                                                       |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | **Default Value**                                                                                                                                                                                                               |
   |                          |                 |                                                                                                                                   |                                                                                                                                                                                                                                 |
   |                          |                 |                                                                                                                                   | N/A                                                                                                                                                                                                                             |
   +--------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _createrocketmqmigrationtask__request_migrationrocketmqtopicconfig:

.. table:: **Table 4** MigrationRocketMqTopicConfig

   +-------------------+-----------------+-----------------+----------------------------------------------------+
   | Parameter         | Mandatory       | Type            | Description                                        |
   +===================+=================+=================+====================================================+
   | topic_name        | No              | String          | **Definition**                                     |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | Topic name.                                        |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Constraints**                                    |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Range**                                          |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Default Value**                                  |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   +-------------------+-----------------+-----------------+----------------------------------------------------+
   | order             | No              | Boolean         | **Definition**                                     |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | Whether messages are ordered.                      |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Constraints**                                    |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Range**                                          |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | -  **true**: Yes                                   |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | -  false" No                                       |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Default Value**                                  |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | false                                              |
   +-------------------+-----------------+-----------------+----------------------------------------------------+
   | perm              | No              | Integer         | **Definition**                                     |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | Topic permissions.                                 |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Constraints**                                    |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Range**                                          |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | -  **PUB**: publish permission.                    |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | -  **SUB**: subscribe permission.                  |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | -  **PUB|SUB**: subscribe and publish permissions. |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | -  **DENY**: no permission.                        |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Default Value**                                  |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | 6                                                  |
   +-------------------+-----------------+-----------------+----------------------------------------------------+
   | read_queue_nums   | No              | Integer         | **Definition**                                     |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | Number of read queues.                             |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Constraints**                                    |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Range**                                          |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Default Value**                                  |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | 16                                                 |
   +-------------------+-----------------+-----------------+----------------------------------------------------+
   | write_queue_nums  | No              | Integer         | **Definition**                                     |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | Number of write queues.                            |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Constraints**                                    |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Range**                                          |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Default Value**                                  |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | 16                                                 |
   +-------------------+-----------------+-----------------+----------------------------------------------------+
   | topic_filter_type | No              | String          | **Definition**                                     |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | Topic filtering type.                              |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Constraints**                                    |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Range**                                          |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | -  **SINGLE_TAG**: single tag                      |
   |                   |                 |                 |                                                    |
   |                   |                 |                 |    -  **MULTI_TAG**: multiple tags                 |
   |                   |                 |                 |                                                    |
   |                   |                 |                 |    **Default Value**                               |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   +-------------------+-----------------+-----------------+----------------------------------------------------+
   | topic_sys_flag    | No              | Integer         | **Definition**                                     |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | Topic system flag.                                 |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Constraints**                                    |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Range**                                          |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | N/A                                                |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | **Default Value**                                  |
   |                   |                 |                 |                                                    |
   |                   |                 |                 | 0                                                  |
   +-------------------+-----------------+-----------------+----------------------------------------------------+

.. _createrocketmqmigrationtask__request_migrationrocketmqsubscriptiongroup:

.. table:: **Table 5** MigrationRocketMqSubscriptionGroup

   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+
   | Parameter                          | Mandatory       | Type            | Description                                             |
   +====================================+=================+=================+=========================================================+
   | group_name                         | No              | String          | **Definition**                                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | Consumer group name.                                    |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Constraints**                                         |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Range**                                               |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Default Value**                                       |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+
   | consume_broadcast_enable           | No              | Boolean         | **Definition**                                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | Whether to allow broadcast.                             |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Constraints**                                         |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Range**                                               |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | -  **true**: Yes                                        |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | -  **false**: No                                        |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Default Value**                                       |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+
   | consume_enable                     | No              | Boolean         | **Definition**                                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | Whether to enable consumption.                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Constraints**                                         |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Range**                                               |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | -  **true**: Yes                                        |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | -  **false**: No                                        |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Default Value**                                       |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | true                                                    |
   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+
   | consume_from_min_enable            | No              | Boolean         | **Definition**                                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | Whether to enable consumption from the earliest offset. |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Constraints**                                         |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Range**                                               |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | -  **true**: Yes                                        |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | -  **false**: No                                        |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Default Value**                                       |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | true                                                    |
   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+
   | notify_consumer_ids_changed_enable | No              | Boolean         | **Definition**                                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | Whether to notify consumer ID changes.                  |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Constraints**                                         |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Range**                                               |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | -  **true**: Yes                                        |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | -  **false**: No                                        |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Default Value**                                       |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | true                                                    |
   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+
   | retry_max_times                    | No              | Integer         | **Definition**                                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | Maximum number of consumption retries.                  |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Constraints**                                         |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Range**                                               |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Default Value**                                       |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | 16                                                      |
   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+
   | retry_queue_nums                   | No              | Integer         | **Definition**                                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | Maximum number of consumption retries.                  |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Constraints**                                         |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Range**                                               |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Default Value**                                       |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | 1                                                       |
   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+
   | which_broker_when_consume_slow     | No              | Long            | **Definition**                                          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | ID of the broker selected for slow consumption          |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Constraints**                                         |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Range**                                               |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | N/A                                                     |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | **Default Value**                                       |
   |                                    |                 |                 |                                                         |
   |                                    |                 |                 | 1                                                       |
   +------------------------------------+-----------------+-----------------+---------------------------------------------------------+

.. _createrocketmqmigrationtask__request_migrationrabbitvhostmetadata:

.. table:: **Table 6** MigrationRabbitVhostMetadata

   +-----------------+-----------------+-----------------+--------------------+
   | Parameter       | Mandatory       | Type            | Description        |
   +=================+=================+=================+====================+
   | name            | No              | String          | **Definition**     |
   |                 |                 |                 |                    |
   |                 |                 |                 | Virtual host name. |
   |                 |                 |                 |                    |
   |                 |                 |                 | **Constraints**    |
   |                 |                 |                 |                    |
   |                 |                 |                 | N/A                |
   |                 |                 |                 |                    |
   |                 |                 |                 | **Range**          |
   |                 |                 |                 |                    |
   |                 |                 |                 | N/A                |
   |                 |                 |                 |                    |
   |                 |                 |                 | **Default Value**  |
   |                 |                 |                 |                    |
   |                 |                 |                 | N/A                |
   +-----------------+-----------------+-----------------+--------------------+

.. _createrocketmqmigrationtask__request_migrationrabbitqueuemetadata:

.. table:: **Table 7** MigrationRabbitQueueMetadata

   +-----------------+-----------------+-----------------+-------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                         |
   +=================+=================+=================+=====================================+
   | vhost           | No              | String          | **Definition**                      |
   |                 |                 |                 |                                     |
   |                 |                 |                 | Virtual host name.                  |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Constraints**                     |
   |                 |                 |                 |                                     |
   |                 |                 |                 | N/A                                 |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Range**                           |
   |                 |                 |                 |                                     |
   |                 |                 |                 | N/A                                 |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Default Value**                   |
   |                 |                 |                 |                                     |
   |                 |                 |                 | N/A                                 |
   +-----------------+-----------------+-----------------+-------------------------------------+
   | name            | No              | String          | **Definition**                      |
   |                 |                 |                 |                                     |
   |                 |                 |                 | Queue name.                         |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Constraints**                     |
   |                 |                 |                 |                                     |
   |                 |                 |                 | N/A                                 |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Range**                           |
   |                 |                 |                 |                                     |
   |                 |                 |                 | N/A                                 |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Default Value**                   |
   |                 |                 |                 |                                     |
   |                 |                 |                 | N/A                                 |
   +-----------------+-----------------+-----------------+-------------------------------------+
   | durable         | No              | Boolean         | **Definition**                      |
   |                 |                 |                 |                                     |
   |                 |                 |                 | Whether to enable data persistence. |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Constraints**                     |
   |                 |                 |                 |                                     |
   |                 |                 |                 | N/A                                 |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Range**                           |
   |                 |                 |                 |                                     |
   |                 |                 |                 | -  **true**: Yes                    |
   |                 |                 |                 |                                     |
   |                 |                 |                 | -  **false**: No                    |
   |                 |                 |                 |                                     |
   |                 |                 |                 | **Default Value**                   |
   |                 |                 |                 |                                     |
   |                 |                 |                 | N/A                                 |
   +-----------------+-----------------+-----------------+-------------------------------------+

.. _createrocketmqmigrationtask__request_migrationrabbitexchangemetadata:

.. table:: **Table 8** MigrationRabbitExchangeMetadata

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                           |
   +=================+=================+=================+=======================================================================================================================+
   | vhost           | No              | String          | **Definition**                                                                                                        |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | Virtual host name.                                                                                                    |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Constraints**                                                                                                       |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Range**                                                                                                             |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Default Value**                                                                                                     |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | name            | No              | String          | **Definition**                                                                                                        |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | Exchange name.                                                                                                        |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Constraints**                                                                                                       |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Range**                                                                                                             |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Default Value**                                                                                                     |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | type            | No              | String          | **Definition**                                                                                                        |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | Exchange type.                                                                                                        |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Constraints**                                                                                                       |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Range**                                                                                                             |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | -  **topic**: Fuzzy match by routing key is supported.                                                                |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | -  **direct**: Messages are routed in exact match by routing key.                                                     |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | -  **fanout**: broadcast mode. Messages are sent to all bound queues, regardless of routing keys.                     |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | -  **headers**: Routing is based on the key-value pair in the message header (headers) instead of on the routing key. |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Default Value**                                                                                                     |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | durable         | No              | Boolean         | **Definition**                                                                                                        |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | Whether to enable data persistence.                                                                                   |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Constraints**                                                                                                       |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Range**                                                                                                             |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | -  **true**: Yes                                                                                                      |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | -  **false**: No                                                                                                      |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Default Value**                                                                                                     |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+

.. _createrocketmqmigrationtask__request_migrationrabbitbindingmetadata:

.. table:: **Table 9** MigrationRabbitBindingMetadata

   +------------------+-----------------+-----------------+--------------------+
   | Parameter        | Mandatory       | Type            | Description        |
   +==================+=================+=================+====================+
   | vhost            | No              | String          | **Definition**     |
   |                  |                 |                 |                    |
   |                  |                 |                 | Virtual host name. |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Constraints**    |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Range**          |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Default Value**  |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   +------------------+-----------------+-----------------+--------------------+
   | source           | No              | String          | **Definition**     |
   |                  |                 |                 |                    |
   |                  |                 |                 | Message source.    |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Constraints**    |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Range**          |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Default Value**  |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   +------------------+-----------------+-----------------+--------------------+
   | destination      | No              | String          | **Definition**     |
   |                  |                 |                 |                    |
   |                  |                 |                 | Message target.    |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Constraints**    |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Range**          |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Default Value**  |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   +------------------+-----------------+-----------------+--------------------+
   | destination_type | No              | String          | **Definition**     |
   |                  |                 |                 |                    |
   |                  |                 |                 | Target type.       |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Constraints**    |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Range**          |
   |                  |                 |                 |                    |
   |                  |                 |                 | -  **exchange**    |
   |                  |                 |                 |                    |
   |                  |                 |                 | -  **queue**       |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Default Value**  |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   +------------------+-----------------+-----------------+--------------------+
   | routing_key      | No              | String          | **Definition**     |
   |                  |                 |                 |                    |
   |                  |                 |                 | Routing key.       |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Constraints**    |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Range**          |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   |                  |                 |                 |                    |
   |                  |                 |                 | **Default Value**  |
   |                  |                 |                 |                    |
   |                  |                 |                 | N/A                |
   +------------------+-----------------+-----------------+--------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 10** Response body parameters

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | task_id               | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Task ID.              |
   |                       |                       |                       |
   |                       |                       | **Constraints**       |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   |                       |                       |                       |
   |                       |                       | **Range**             |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   |                       |                       |                       |
   |                       |                       | **Default Value**     |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   +-----------------------+-----------------------+-----------------------+

Example Requests
----------------

-  Creating a metadata migration task to migrate the metadata from other vendors' or self-built RocketMQ instances to DMS for RocketMQ.

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/instances/{instance_id}/metadata?overwrite=true&name=task-123&type=rocketmq

      {
        "topic_config_table" : {
          "topic-test1" : {
            "order" : false,
            "perm" : 6,
            "read_queue_nums" : 3,
            "topic_filter_type" : "SINGLE_TAG",
            "topic_name" : "topic-test1",
            "topic_sys_flag" : 0,
            "write_queue_nums" : 3
          }
        },
        "subscription_group_table" : {
          "group-test1" : {
            "consume_broadcast_enable" : true,
            "consume_enable" : true,
            "consume_from_min_enable" : true,
            "group_name" : "group-test1",
            "notify_consumer_ids_changed_enable" : true,
            "retry_max_times" : 2,
            "retry_queue_nums" : 1,
            "which_broker_when_consume_slow" : 1
          }
        }
      }

-  Creating a metadata migration task to migrate the metadata of RabbitMQ instances to DMS for RocketMQ.

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/instances/{instance_id}/metadata?overwrite=true&name=task-123&type=rabbitToRocket

      {
        "vhosts" : [ {
          "name" : "DeleteVhost123"
        } ],
        "queues" : [ {
          "name" : "test-001",
          "vhost" : "/",
          "durable" : false
        } ],
        "exchanges" : [ {
          "name" : "direct",
          "vhost" : "/",
          "type" : "topic",
          "durable" : false
        } ],
        "bindings" : [ {
          "source" : "direct",
          "vhost" : "/",
          "destination" : "test-001",
          "destination_type" : "queue",
          "routing_key" : "test-001"
        } ]
      }

Example Responses
-----------------

**Status code: 200**

Successful

.. code-block::

   {
     "task_id" : "6cf4dcd3-8471-4139-8b5b-8a3a71f704c7"
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         Successful
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
