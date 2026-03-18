:original_name: CreateTopicOrBatchDeleteTopic.html

.. _CreateTopicOrBatchDeleteTopic:

Creating a Topic or Deleting Topics in Batches
==============================================

Function
--------

This API is used to create a topic or delete topics in batches.

URI
---

POST /v2/{project_id}/instances/{instance_id}/topics

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

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                    |
   +=================+=================+=================+================================================================================================+
   | action          | No              | String          | **Definition**                                                                                 |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | This parameter is used to delete topics in batches. If it is not set, a topic will be created. |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | **Constraints**                                                                                |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | N/A                                                                                            |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | **Range**                                                                                      |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | -  **delete**: batch deletion                                                                  |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | -  Left blank: topic creation                                                                  |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | **Default Value**                                                                              |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | N/A                                                                                            |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request body parameters

   +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                                           |
   +=================+=================+==================+=======================================================================================================================+
   | name            | No              | String           | **Definition**                                                                                                        |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | Topic name.                                                                                                           |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | **Constraints**                                                                                                       |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | Enter 3 to 64 characters. Use only letters, digits, percent (%), vertical bars (|), hyphens (-), and underscores (_). |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | Mandatory for topic creation.                                                                                         |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | **Range**                                                                                                             |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | N/A                                                                                                                   |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | **Default Value**                                                                                                     |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | N/A                                                                                                                   |
   +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------+
   | queue_num       | No              | Number           | Total number of queues. The range is 1-50.                                                                            |
   +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------+
   | message_type    | No              | String           | Message type (This parameter is mandatory only for RocketMQ 5.x instances).                                           |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | Options:                                                                                                              |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | -  **NORMAL** (normal messages)                                                                                       |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | -  **FIFO** (ordered messages)                                                                                        |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | -  **DELAY** (scheduled messages)                                                                                     |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | -  **TRANSACTION** (transactional messages)                                                                           |
   +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------+
   | topics          | No              | Array of strings | **Definition**                                                                                                        |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | Topic list. This parameter is used when topics are deleted in batches.                                                |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | **Constraints**                                                                                                       |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | N/A                                                                                                                   |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | **Range**                                                                                                             |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | N/A                                                                                                                   |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | **Default Value**                                                                                                     |
   |                 |                 |                  |                                                                                                                       |
   |                 |                 |                  | N/A                                                                                                                   |
   +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-----------------------+-----------------------+--------------------------------+
   | Parameter             | Type                  | Description                    |
   +=======================+=======================+================================+
   | id                    | String                | **Definition**                 |
   |                       |                       |                                |
   |                       |                       | Topic name.                    |
   |                       |                       |                                |
   |                       |                       | **Constraints**                |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   |                       |                       |                                |
   |                       |                       | **Range**                      |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   |                       |                       |                                |
   |                       |                       | **Default Value**              |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   +-----------------------+-----------------------+--------------------------------+
   | job_id                | String                | **Definition**                 |
   |                       |                       |                                |
   |                       |                       | ID of the topic deletion task. |
   |                       |                       |                                |
   |                       |                       | **Constraints**                |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   |                       |                       |                                |
   |                       |                       | **Range**                      |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   |                       |                       |                                |
   |                       |                       | **Default Value**              |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   +-----------------------+-----------------------+--------------------------------+

Example Requests
----------------

-  Creating topics for a RocketMQ 5.x instance in batch

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/instances/{instance_id}/topics

      {
        "name" : "topic-test"
      }

-  Deleting topics of a RocketMQ 5.x instance in a batch

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/instances/{instance_id}/topics?action=delete

      {
        "topics" : [ "topic01", "topic02" ]
      }

Example Responses
-----------------

**Status code: 200**

Topic created.

-  Successfully created the topic

   .. code-block::

      {
        "id" : "topic-test"
      }

-  Successfully deleted topics in a batch

   .. code-block::

      {
        "job_id" : "8abfa7b299f0497c0199f0dc0a9a092b"
      }

Status Codes
------------

=========== ==============
Status Code Description
=========== ==============
200         Topic created.
=========== ==============

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
