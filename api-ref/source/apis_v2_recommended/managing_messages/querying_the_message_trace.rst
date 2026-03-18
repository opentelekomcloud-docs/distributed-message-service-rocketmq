:original_name: ListMessageTraceForRocketMq.html

.. _ListMessageTraceForRocketMq:

Querying the Message Trace
==========================

Function
--------

This API is used to query the message trace.

URI
---

GET /v2/{project_id}/rocketmq/instances/{instance_id}/trace

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
   | msg_id          | Yes             | String          | **Definition**                                                                                      |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | Message ID.                                                                                         |
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
   |                 |                 |                 | 10                                                                                                  |
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
   |                 |                 |                 | 0                                                                                                   |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------------------------------------------------------------+------------------------------+
   | Parameter             | Type                                                                        | Description                  |
   +=======================+=============================================================================+==============================+
   | total                 | Number                                                                      | **Definition**               |
   |                       |                                                                             |                              |
   |                       |                                                                             | Total number.                |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Constraints**              |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Range**                    |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Default Value**            |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------+------------------------------+
   | next_offset           | Integer                                                                     | **Definition**               |
   |                       |                                                                             |                              |
   |                       |                                                                             | Offset of the next page.     |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Constraints**              |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Range**                    |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Default Value**            |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------+------------------------------+
   | previous_offset       | Integer                                                                     | **Definition**               |
   |                       |                                                                             |                              |
   |                       |                                                                             | Offset of the previous page. |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Constraints**              |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Range**                    |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Default Value**            |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------+------------------------------+
   | trace                 | Array of :ref:`trace <listmessagetraceforrocketmq__response_trace>` objects | **Definition**               |
   |                       |                                                                             |                              |
   |                       |                                                                             | Message trace list.          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Constraints**              |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Range**                    |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   |                       |                                                                             |                              |
   |                       |                                                                             | **Default Value**            |
   |                       |                                                                             |                              |
   |                       |                                                                             | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------+------------------------------+

.. _listmessagetraceforrocketmq__response_trace:

.. table:: **Table 4** trace

   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | Parameter              | Type                  | Description                                                                 |
   +========================+=======================+=============================================================================+
   | success                | Boolean               | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Successful or not.                                                          |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | -  **true**: successful                                                     |
   |                        |                       |                                                                             |
   |                        |                       | -  **false**: failed                                                        |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | trace_type             | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Trace type.                                                                 |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | -  **Pub**: The producer successfully sends messages.                       |
   |                        |                       |                                                                             |
   |                        |                       | -  **SubBefore**: The consumer is ready to consume messages.                |
   |                        |                       |                                                                             |
   |                        |                       | -  **SubAfter**: The consumer finishes consuming messages.                  |
   |                        |                       |                                                                             |
   |                        |                       | -  **EndTransaction**: Transactional messages are committed or rolled back. |
   |                        |                       |                                                                             |
   |                        |                       | -  **Receive**: The service side receives messages.                         |
   |                        |                       |                                                                             |
   |                        |                       | -  **Ack**: The consumer manually acknowledges consumption.                 |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | timestamp              | Number                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Time.                                                                       |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | group_name             | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Producer group or consumer group.                                           |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | cost_time              | Number                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Duration.                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | request_id             | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Request ID.                                                                 |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | consume_status         | Number                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Consumption status.                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | -  **0**: Successful                                                        |
   |                        |                       |                                                                             |
   |                        |                       | -  **1**: Timeout                                                           |
   |                        |                       |                                                                             |
   |                        |                       | -  **2**: Exception                                                         |
   |                        |                       |                                                                             |
   |                        |                       | -  **3**: Null                                                              |
   |                        |                       |                                                                             |
   |                        |                       | -  **5**: Failed                                                            |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | topic                  | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Topic name.                                                                 |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | msg_id                 | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Message ID.                                                                 |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | offset_msg_id          | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Offset message ID.                                                          |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | tags                   | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Message tag.                                                                |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | keys                   | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Message keys.                                                               |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | store_host             | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | IP address of the host that stores the message.                             |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | client_host            | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | IP address of the host that generates the message.                          |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | retry_times            | Integer               | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Number of retry times.                                                      |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | body_length            | Number                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Message body length.                                                        |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | msg_type               | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Message type.                                                               |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | -  **Normal_Msg**: normal message                                           |
   |                        |                       |                                                                             |
   |                        |                       | -  **Trans_Msg_Half**: half message                                         |
   |                        |                       |                                                                             |
   |                        |                       | -  **Trans_msg_Commit**: delivered message                                  |
   |                        |                       |                                                                             |
   |                        |                       | -  **Delay_Msg**: delayed message                                           |
   |                        |                       |                                                                             |
   |                        |                       | -  **Order_Msg**: ordered message                                           |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | transaction_state      | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Transaction status.                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | -  COMMIT_MESSAGE                                                           |
   |                        |                       |                                                                             |
   |                        |                       | -  ROLLBACK_MESSAGE                                                         |
   |                        |                       |                                                                             |
   |                        |                       | -  UNKNOW                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | transaction_id         | String                | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Transaction ID.                                                             |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+
   | from_transaction_check | Boolean               | **Definition**                                                              |
   |                        |                       |                                                                             |
   |                        |                       | Whether the response is a transaction check response.                       |
   |                        |                       |                                                                             |
   |                        |                       | **Constraints**                                                             |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   |                        |                       |                                                                             |
   |                        |                       | **Range**                                                                   |
   |                        |                       |                                                                             |
   |                        |                       | -  **true**: Yes                                                            |
   |                        |                       |                                                                             |
   |                        |                       | -  **false**: No                                                            |
   |                        |                       |                                                                             |
   |                        |                       | **Default Value**                                                           |
   |                        |                       |                                                                             |
   |                        |                       | N/A                                                                         |
   +------------------------+-----------------------+-----------------------------------------------------------------------------+

Example Requests
----------------

Querying the message trace of a RocketMQ instance

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/trace?msg_id={msg_id}

Example Responses
-----------------

**Status code: 200**

Queried.

.. code-block::

   {
     "total" : 1,
     "next_offset" : -1,
     "previous_offset" : -1,
     "trace" : [ {
       "success" : true,
       "trace_type" : "Pub",
       "timestamp" : 1634822858013,
       "group_name" : "ProducerGroupName",
       "cost_time" : 47,
       "request_id" : "644F0069C829287CBBF26B9A54390000",
       "consume_status" : 0,
       "topic" : "aaaaa",
       "msg_id" : "7F000001561018B4AAC26B9A0D1D0004",
       "offset_msg_id" : "C0A8011700002774000000000000BE12",
       "tags" : "TagA",
       "keys" : "OrderID188",
       "store_host" : "192.168.0.1:10101",
       "client_host" : "127.0.0.1",
       "retry_times" : 0,
       "body_length" : 11,
       "msg_type" : "Normal_Msg",
       "transaction_state" : null,
       "transaction_id" : null,
       "from_transaction_check" : false
     } ]
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         Queried.
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
