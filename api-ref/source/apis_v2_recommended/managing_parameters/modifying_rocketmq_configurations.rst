:original_name: UpdateRocketMqConfigs.html

.. _UpdateRocketMqConfigs:

Modifying RocketMQ Configurations
=================================

Function
--------

This API is used to modify RocketMQ configurations.

URI
---

PUT /v2/{project_id}/rocketmq/instances/{instance_id}/configs

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

Request Parameters
------------------

.. table:: **Table 2** Request body parameters

   +------------------+-----------------+----------------------------------------------------------------------------------------------+-------------------------+
   | Parameter        | Mandatory       | Type                                                                                         | Description             |
   +==================+=================+==============================================================================================+=========================+
   | rocketmq_configs | Yes             | Array of :ref:`RocketMQConfigReq <updaterocketmqconfigs__request_rocketmqconfigreq>` objects | **Definition**          |
   |                  |                 |                                                                                              |                         |
   |                  |                 |                                                                                              | RocketMQ configuration. |
   |                  |                 |                                                                                              |                         |
   |                  |                 |                                                                                              | **Constraints**         |
   |                  |                 |                                                                                              |                         |
   |                  |                 |                                                                                              | N/A                     |
   |                  |                 |                                                                                              |                         |
   |                  |                 |                                                                                              | **Range**               |
   |                  |                 |                                                                                              |                         |
   |                  |                 |                                                                                              | N/A                     |
   |                  |                 |                                                                                              |                         |
   |                  |                 |                                                                                              | **Default Value**       |
   |                  |                 |                                                                                              |                         |
   |                  |                 |                                                                                              | N/A                     |
   +------------------+-----------------+----------------------------------------------------------------------------------------------+-------------------------+

.. _updaterocketmqconfigs__request_rocketmqconfigreq:

.. table:: **Table 3** RocketMQConfigReq

   +-----------------+-----------------+-----------------+--------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                          |
   +=================+=================+=================+======================================+
   | name            | Yes             | String          | **Definition**                       |
   |                 |                 |                 |                                      |
   |                 |                 |                 | RocketMQ configuration name.         |
   |                 |                 |                 |                                      |
   |                 |                 |                 | **Constraints**                      |
   |                 |                 |                 |                                      |
   |                 |                 |                 | N/A                                  |
   |                 |                 |                 |                                      |
   |                 |                 |                 | **Range**                            |
   |                 |                 |                 |                                      |
   |                 |                 |                 | N/A                                  |
   |                 |                 |                 |                                      |
   |                 |                 |                 | **Default Value**                    |
   |                 |                 |                 |                                      |
   |                 |                 |                 | N/A                                  |
   +-----------------+-----------------+-----------------+--------------------------------------+
   | value           | Yes             | String          | **Definition**                       |
   |                 |                 |                 |                                      |
   |                 |                 |                 | RocketMQ configuration target value. |
   |                 |                 |                 |                                      |
   |                 |                 |                 | **Constraints**                      |
   |                 |                 |                 |                                      |
   |                 |                 |                 | N/A                                  |
   |                 |                 |                 |                                      |
   |                 |                 |                 | **Range**                            |
   |                 |                 |                 |                                      |
   |                 |                 |                 | N/A                                  |
   |                 |                 |                 |                                      |
   |                 |                 |                 | **Default Value**                    |
   |                 |                 |                 |                                      |
   |                 |                 |                 | N/A                                  |
   +-----------------+-----------------+-----------------+--------------------------------------+

Response Parameters
-------------------

**Status code: 204**

Successful.

None

Example Requests
----------------

Modifying RocketMQ configurations with file retention period changed to 72 hours.

.. code-block:: text

   PUT  https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/configs

   {
     "rocketmq_configs" : [ {
       "name" : "fileReservedTime",
       "value" : 72
     } ]
   }

Example Responses
-----------------

None

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
204         Successful.
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
