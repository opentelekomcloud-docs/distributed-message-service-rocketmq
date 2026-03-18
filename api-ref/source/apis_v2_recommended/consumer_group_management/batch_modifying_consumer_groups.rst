:original_name: BatchUpdateConsumerGroup.html

.. _BatchUpdateConsumerGroup:

Batch Modifying Consumer Groups
===============================

Function
--------

This API is used to modify consumer groups in batches.

URI
---

PUT /v2/{project_id}/instances/{instance_id}/groups

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

   +-----------------+-----------------+---------------------------------------------------------------------------------------------------------------+----------------------+
   | Parameter       | Mandatory       | Type                                                                                                          | Description          |
   +=================+=================+===============================================================================================================+======================+
   | groups          | No              | Array of :ref:`BatchUpdateConsumerGroup <batchupdateconsumergroup__request_batchupdateconsumergroup>` objects | **Definition**       |
   |                 |                 |                                                                                                               |                      |
   |                 |                 |                                                                                                               | Consumer group list. |
   |                 |                 |                                                                                                               |                      |
   |                 |                 |                                                                                                               | **Constraints**      |
   |                 |                 |                                                                                                               |                      |
   |                 |                 |                                                                                                               | N/A                  |
   |                 |                 |                                                                                                               |                      |
   |                 |                 |                                                                                                               | **Range**            |
   |                 |                 |                                                                                                               |                      |
   |                 |                 |                                                                                                               | N/A                  |
   |                 |                 |                                                                                                               |                      |
   |                 |                 |                                                                                                               | **Default Value**    |
   |                 |                 |                                                                                                               |                      |
   |                 |                 |                                                                                                               | N/A                  |
   +-----------------+-----------------+---------------------------------------------------------------------------------------------------------------+----------------------+

.. _batchupdateconsumergroup__request_batchupdateconsumergroup:

.. table:: **Table 3** BatchUpdateConsumerGroup

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                |
   +=================+=================+=================+============================================================================================================================================+
   | name            | Yes             | String          | Consumer group name. Enter 3 to 64 characters. Use only letters, digits, percent (%), vertical bars (|), hyphens (-), and underscores (_). |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | broadcast       | No              | Boolean         | Whether to broadcast.                                                                                                                      |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | retry_max_time  | No              | Integer         | Maximum number of retries. The value ranges from 1 to 16.                                                                                  |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | enabled         | No              | Boolean         | Whether consumption is allowed.                                                                                                            |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | consume_orderly | No              | Boolean         | **Definition**                                                                                                                             |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | Whether to enable orderly consumption (mandatory only for RocketMQ 5.x instances).                                                         |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | **Constraints**                                                                                                                            |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | N/A                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | **Range**                                                                                                                                  |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | -  **true**: Yes                                                                                                                           |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | -  **false**: No                                                                                                                           |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | **Default Value**                                                                                                                          |
   |                 |                 |                 |                                                                                                                                            |
   |                 |                 |                 | N/A                                                                                                                                        |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+
   | group_desc      | No              | String          | Consumer group description. 0 to 200 characters.                                                                                           |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | job_id                | String                | **Definition**        |
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

Batch modifying parameters of consumer groups, with max. retries of group1 changed to 16.

.. code-block:: text

   PUT https://{endpoint}/v2/{project_id}/instances/{instance_id}/groups

   {
     "groups" : [ {
       "enabled" : true,
       "broadcast" : false,
       "name" : "group1",
       "retry_max_time" : 16
     } ]
   }

Example Responses
-----------------

**Status code: 200**

Consumer groups modified successfully.

.. code-block::

   {
     "job_id" : "8abfa7b27da211df017da340427b0979"
   }

Status Codes
------------

=========== ======================================
Status Code Description
=========== ======================================
200         Consumer groups modified successfully.
=========== ======================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
