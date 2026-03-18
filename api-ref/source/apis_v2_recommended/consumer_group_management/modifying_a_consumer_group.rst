:original_name: UpdateConsumerGroup.html

.. _UpdateConsumerGroup:

Modifying a Consumer Group
==========================

Function
--------

This API is used to modify parameters of a specified consumer group.

URI
---

PUT /v2/{project_id}/instances/{instance_id}/groups/{group}

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
   | group           | Yes             | String          | Consumer group name.                                                                                                             |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request body parameters

   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                       |
   +=================+=================+==================+===================================================================================================+
   | enabled         | Yes             | Boolean          | Whether a message can be consumed.                                                                |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------+
   | broadcast       | Yes             | Boolean          | Whether to broadcast.                                                                             |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------+
   | brokers         | No              | Array of strings | **Definition**                                                                                    |
   |                 |                 |                  |                                                                                                   |
   |                 |                 |                  | List of associated brokers.                                                                       |
   |                 |                 |                  |                                                                                                   |
   |                 |                 |                  | **Constraints**                                                                                   |
   |                 |                 |                  |                                                                                                   |
   |                 |                 |                  | N/A                                                                                               |
   |                 |                 |                  |                                                                                                   |
   |                 |                 |                  | **Range**                                                                                         |
   |                 |                 |                  |                                                                                                   |
   |                 |                 |                  | N/A                                                                                               |
   |                 |                 |                  |                                                                                                   |
   |                 |                 |                  | **Default Value**                                                                                 |
   |                 |                 |                  |                                                                                                   |
   |                 |                 |                  | N/A                                                                                               |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------+
   | name            | No              | String           | Consumer group whose parameters are to be modified. (The consumer group name cannot be modified.) |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------+
   | retry_max_time  | Yes             | Integer          | Maximum number of retries. Value range: 1 to 16.                                                  |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 204**

The specified consumer group is modified.

None

Example Requests
----------------

Changing consumer-group-test's max. retries to 16

.. code-block:: text

   PUT https://{endpoint}/v2/{project_id}/instances/{instance_id}/groups/{group}

   {
     "enabled" : true,
     "retry_max_time" : 16,
     "broadcast" : true
   }

Example Responses
-----------------

None

Status Codes
------------

=========== =========================================
Status Code Description
=========== =========================================
204         The specified consumer group is modified.
=========== =========================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
