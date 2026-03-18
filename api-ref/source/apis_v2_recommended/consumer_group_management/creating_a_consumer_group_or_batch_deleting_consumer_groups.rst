:original_name: CreateConsumerGroupOrBatchDeleteConsumerGroup.html

.. _CreateConsumerGroupOrBatchDeleteConsumerGroup:

Creating a Consumer Group or Batch Deleting Consumer Groups
===========================================================

Function
--------

This API is used to create a consumer group or batch deleting consumer groups.

URI
---

POST /v2/{project_id}/instances/{instance_id}/groups

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

   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                                                     |
   +===========+===========+========+=================================================================================================================================================================+
   | action    | No        | String | This parameter is used to delete consumer groups in batches. If it is not set, a consumer group will be created. **delete**: Delete consumer groups in batches. |
   +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request body parameters

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                           |
   +=================+=================+=================+=======================================================================================================================+
   | job_id          | No              | String          | **Definition**                                                                                                        |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | List of consumer groups to be deleted.                                                                                |
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
   |                 |                 |                 | Consumer group name.                                                                                                  |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Constraints**                                                                                                       |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | Enter 3 to 64 characters. Use only letters, digits, percent (%), vertical bars (|), hyphens (-), and underscores (_). |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | Mandatory for consumer group creation.                                                                                |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Range**                                                                                                             |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Default Value**                                                                                                     |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | N/A                                                                                                                   |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | broadcast       | No              | Boolean         | Whether to broadcast.                                                                                                 |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | retry_max_time  | No              | Integer         | Maximum number of retries (1 to 16 characters).                                                                       |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | enabled         | No              | Boolean         | Whether consumption is allowed.                                                                                       |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | consume_orderly | No              | Boolean         | **Definition**                                                                                                        |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | Whether orderly consumption is enabled.                                                                               |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | **Constraints**                                                                                                       |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | This parameter is required only for RocketMQ 5.x instances.                                                           |
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
   | group_desc      | No              | String          | Consumer group description (0 to 200 characters).                                                                     |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-----------------------+-----------------------+-----------------------------------------+
   | Parameter             | Type                  | Description                             |
   +=======================+=======================+=========================================+
   | job_id                | String                | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | ID of the consumer group deletion task. |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | name                  | String                | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Name of the created consumer group.     |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+

Example Requests
----------------

-  Creating a consumer group with max. 16 retries.

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/instances/{instance_id}/groups

      {
        "name" : "consumer-group-test",
        "broadcast" : false,
        "retry_max_time" : 16
      }

-  Deleting consumer group consumer-group-test.

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/instances/{instance_id}/groups?action=delete

Example Responses
-----------------

**Status code: 200**

A consumer group is created or multiple consumer groups are deleted in batches.

-  Creating a consumer group

   .. code-block::

      {
        "name" : "consumer-group-test"
      }

-  Consumer groups deleted

   .. code-block::

      {
        "job_id" : "ff8080829ae99a23019b240d388b4e47"
      }

Status Codes
------------

+-------------+---------------------------------------------------------------------------------+
| Status Code | Description                                                                     |
+=============+=================================================================================+
| 200         | A consumer group is created or multiple consumer groups are deleted in batches. |
+-------------+---------------------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
