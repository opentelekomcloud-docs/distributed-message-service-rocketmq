:original_name: ShowRocketMqConfigs.html

.. _ShowRocketMqConfigs:

Querying RocketMQ Configurations
================================

Function
--------

This API is used to query RocketMQ configurations. Configuration details will be returned.

URI
---

GET /v2/{project_id}/rocketmq/instances/{instance_id}/configs

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

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                         |
   +=================+=================+=================+=====================================================================================================+
   | limit           | No              | Integer         | **Definition**                                                                                      |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | Number of records to query.                                                                         |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                     |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Range**                                                                                           |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                   |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------+
   | offset          | No              | Integer         | **Definition**                                                                                      |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | Offset, which is the position where the query starts. The value must be greater than or equal to 0. |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                     |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Range**                                                                                           |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                   |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------------------------------------------------------------------------------+------------------------------+
   | Parameter             | Type                                                                                          | Description                  |
   +=======================+===============================================================================================+==============================+
   | total                 | Number                                                                                        | **Definition**               |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | Total number.                |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Constraints**              |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Range**                    |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Default Value**            |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------------------------+------------------------------+
   | next_offset           | Integer                                                                                       | **Definition**               |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | Offset of the next page.     |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Constraints**              |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Range**                    |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Default Value**            |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------------------------+------------------------------+
   | previous_offset       | Integer                                                                                       | **Definition**               |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | Offset of the previous page. |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Constraints**              |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Range**                    |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Default Value**            |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------------------------+------------------------------+
   | rocketmq_configs      | Array of :ref:`RocketMQConfigResp <showrocketmqconfigs__response_rocketmqconfigresp>` objects | **Definition**               |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | RocketMQ configuration.      |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Constraints**              |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Range**                    |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | **Default Value**            |
   |                       |                                                                                               |                              |
   |                       |                                                                                               | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------------------------+------------------------------+

.. _showrocketmqconfigs__response_rocketmqconfigresp:

.. table:: **Table 4** RocketMQConfigResp

   +-----------------------+-----------------------+---------------------------------------+
   | Parameter             | Type                  | Description                           |
   +=======================+=======================+=======================================+
   | name                  | String                | **Definition**                        |
   |                       |                       |                                       |
   |                       |                       | RocketMQ configuration name.          |
   |                       |                       |                                       |
   |                       |                       | **Constraints**                       |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Range**                             |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Default Value**                     |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   +-----------------------+-----------------------+---------------------------------------+
   | value                 | String                | **Definition**                        |
   |                       |                       |                                       |
   |                       |                       | RocketMQ configuration current value. |
   |                       |                       |                                       |
   |                       |                       | **Constraints**                       |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Range**                             |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Default Value**                     |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   +-----------------------+-----------------------+---------------------------------------+
   | config_type           | String                | **Definition**                        |
   |                       |                       |                                       |
   |                       |                       | RocketMQ configuration type.          |
   |                       |                       |                                       |
   |                       |                       | **Constraints**                       |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Range**                             |
   |                       |                       |                                       |
   |                       |                       | -  **dynamic**                        |
   |                       |                       |                                       |
   |                       |                       | -  **static**                         |
   |                       |                       |                                       |
   |                       |                       | **Default Value**                     |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   +-----------------------+-----------------------+---------------------------------------+
   | default_value         | String                | **Definition**                        |
   |                       |                       |                                       |
   |                       |                       | RocketMQ configuration default value. |
   |                       |                       |                                       |
   |                       |                       | **Constraints**                       |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Range**                             |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Default Value**                     |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   +-----------------------+-----------------------+---------------------------------------+
   | valid_values          | String                | **Definition**                        |
   |                       |                       |                                       |
   |                       |                       | RocketMQ configuration value range.   |
   |                       |                       |                                       |
   |                       |                       | **Constraints**                       |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Range**                             |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Default Value**                     |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   +-----------------------+-----------------------+---------------------------------------+
   | value_type            | String                | **Definition**                        |
   |                       |                       |                                       |
   |                       |                       | RocketMQ configuration value type.    |
   |                       |                       |                                       |
   |                       |                       | **Constraints**                       |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   |                       |                       |                                       |
   |                       |                       | **Range**                             |
   |                       |                       |                                       |
   |                       |                       | -  **integer**                        |
   |                       |                       |                                       |
   |                       |                       | -  **boolean**                        |
   |                       |                       |                                       |
   |                       |                       | **Default Value**                     |
   |                       |                       |                                       |
   |                       |                       | N/A                                   |
   +-----------------------+-----------------------+---------------------------------------+

Example Requests
----------------

.. code-block:: text

   GET  https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/configs

Example Responses
-----------------

**Status code: 200**

Successful.

.. code-block::

   {
     "total" : 1,
     "next_offset" : -1,
     "previous_offset" : -1,
     "rocketmq_configs" : [ {
       "name" : "fileReservedTime",
       "value" : 48,
       "config_type" : "dynamic",
       "default_value" : 48,
       "valid_values" : "1~720",
       "value_type" : "integer"
     } ]
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         Successful.
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
