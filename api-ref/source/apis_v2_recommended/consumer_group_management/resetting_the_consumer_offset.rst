:original_name: ResetConsumeOffsetForRocketMq.html

.. _ResetConsumeOffsetForRocketMq:

Resetting the Consumer Offset
=============================

Function
--------

This API is used to reset the consumer offset.

URI
---

POST /v2/{project_id}/rocketmq/instances/{instance_id}/groups/{group}/reset-message-offset

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
   | group           | Yes             | String          | **Definition**                                                                                                                   |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | Consumer group name.                                                                                                             |
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

   +-----------------+-----------------+-----------------+--------------------+
   | Parameter       | Mandatory       | Type            | Description        |
   +=================+=================+=================+====================+
   | topic           | Yes             | String          | **Definition**     |
   |                 |                 |                 |                    |
   |                 |                 |                 | Topic to be reset. |
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
   | timestamp       | Yes             | String          | **Definition**     |
   |                 |                 |                 |                    |
   |                 |                 |                 | Reset time.        |
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

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+---------------------------------------------------------------------------------+-----------------------+
   | Parameter             | Type                                                                            | Description           |
   +=======================+=================================================================================+=======================+
   | queues                | Array of :ref:`queues <resetconsumeoffsetforrocketmq__response_queues>` objects | **Definition**        |
   |                       |                                                                                 |                       |
   |                       |                                                                                 | Queues to be reset.   |
   |                       |                                                                                 |                       |
   |                       |                                                                                 | **Constraints**       |
   |                       |                                                                                 |                       |
   |                       |                                                                                 | N/A                   |
   |                       |                                                                                 |                       |
   |                       |                                                                                 | **Range**             |
   |                       |                                                                                 |                       |
   |                       |                                                                                 | N/A                   |
   |                       |                                                                                 |                       |
   |                       |                                                                                 | **Default Value**     |
   |                       |                                                                                 |                       |
   |                       |                                                                                 | N/A                   |
   +-----------------------+---------------------------------------------------------------------------------+-----------------------+

.. _resetconsumeoffsetforrocketmq__response_queues:

.. table:: **Table 4** queues

   +-----------------------+-----------------------+------------------------------------+
   | Parameter             | Type                  | Description                        |
   +=======================+=======================+====================================+
   | broker_name           | String                | **Definition**                     |
   |                       |                       |                                    |
   |                       |                       | Broker where the queue is located. |
   |                       |                       |                                    |
   |                       |                       | **Constraints**                    |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   |                       |                       |                                    |
   |                       |                       | **Range**                          |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   |                       |                       |                                    |
   |                       |                       | **Default Value**                  |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   +-----------------------+-----------------------+------------------------------------+
   | queue_id              | Integer               | **Definition**                     |
   |                       |                       |                                    |
   |                       |                       | Queue ID.                          |
   |                       |                       |                                    |
   |                       |                       | **Constraints**                    |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   |                       |                       |                                    |
   |                       |                       | **Range**                          |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   |                       |                       |                                    |
   |                       |                       | **Default Value**                  |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   +-----------------------+-----------------------+------------------------------------+
   | timestamp_offset      | Long                  | **Definition**                     |
   |                       |                       |                                    |
   |                       |                       | Resets consumer offset.            |
   |                       |                       |                                    |
   |                       |                       | **Constraints**                    |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   |                       |                       |                                    |
   |                       |                       | **Range**                          |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   |                       |                       |                                    |
   |                       |                       | **Default Value**                  |
   |                       |                       |                                    |
   |                       |                       | N/A                                |
   +-----------------------+-----------------------+------------------------------------+

Example Requests
----------------

Resetting consumer offset of topic_01 to the specified time

.. code-block:: text

   POST https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/groups/{group}/reset-message-offset

   {
     "topic" : "topic_01",
     "timestamp" : 1662652800000
   }

Example Responses
-----------------

**Status code: 200**

Consumer offset reset.

.. code-block::

   {
     "queues" : [ {
       "broker_name" : "broker-1",
       "queue_id" : 0,
       "timestamp_offset" : 0
     } ]
   }

Status Codes
------------

=========== ======================
Status Code Description
=========== ======================
200         Consumer offset reset.
=========== ======================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
