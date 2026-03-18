:original_name: ShowOneTopic.html

.. _ShowOneTopic:

Querying a Topic
================

Function
--------

This API is used to query a topic.

URI
---

GET /v2/{project_id}/instances/{instance_id}/topics/{topic}

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
   | topic           | Yes             | String          | Topic name.                                                                                                                      |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------------------+------------------------------------------------------------------+-----------------------------------------------------------+
   | Parameter             | Type                                                             | Description                                               |
   +=======================+==================================================================+===========================================================+
   | name                  | String                                                           | **Definition**                                            |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | Topic name.                                               |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Constraints**                                           |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Range**                                                 |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Default Value**                                         |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   +-----------------------+------------------------------------------------------------------+-----------------------------------------------------------+
   | total_read_queue_num  | Number                                                           | **Definition**                                            |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | Total number of read queues.                              |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Constraints**                                           |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Range**                                                 |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Default Value**                                         |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   +-----------------------+------------------------------------------------------------------+-----------------------------------------------------------+
   | total_write_queue_num | Number                                                           | **Definition**                                            |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | Total number of write queues.                             |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Constraints**                                           |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Range**                                                 |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Default Value**                                         |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   +-----------------------+------------------------------------------------------------------+-----------------------------------------------------------+
   | permission            | String                                                           | **Definition**                                            |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | Permission.                                               |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Constraints**                                           |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Range**                                                 |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | -  **sub**: subscribe permissions.                        |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | -  **pub**: publish permissions.                          |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | -  **all**: subscribe and publish permissions.            |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Default Value**                                         |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   +-----------------------+------------------------------------------------------------------+-----------------------------------------------------------+
   | brokers               | Array of :ref:`brokers <showonetopic__response_brokers>` objects | **Definition**                                            |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | Associated broker.                                        |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Constraints**                                           |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Range**                                                 |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Default Value**                                         |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   +-----------------------+------------------------------------------------------------------+-----------------------------------------------------------+
   | message_type          | String                                                           | **Definition**                                            |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | Message type (available only for RocketMQ 5.x instances). |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Constraints**                                           |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Range**                                                 |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | -  **NORMAL**: normal messages.                           |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | -  **FIFO**: ordered messages.                            |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | -  **DELAY**: scheduled messages.                         |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | -  **TRANSACTION**: transactional messages.               |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | **Default Value**                                         |
   |                       |                                                                  |                                                           |
   |                       |                                                                  | N/A                                                       |
   +-----------------------+------------------------------------------------------------------+-----------------------------------------------------------+

.. _showonetopic__response_brokers:

.. table:: **Table 3** brokers

   +-----------------------+-----------------------+-------------------------+
   | Parameter             | Type                  | Description             |
   +=======================+=======================+=========================+
   | broker_name           | String                | **Definition**          |
   |                       |                       |                         |
   |                       |                       | Broker name.            |
   |                       |                       |                         |
   |                       |                       | **Constraints**         |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   |                       |                       |                         |
   |                       |                       | **Range**               |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   |                       |                       |                         |
   |                       |                       | **Default Value**       |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   +-----------------------+-----------------------+-------------------------+
   | read_queue_num        | Number                | **Definition**          |
   |                       |                       |                         |
   |                       |                       | Number of read queues.  |
   |                       |                       |                         |
   |                       |                       | **Constraints**         |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   |                       |                       |                         |
   |                       |                       | **Range**               |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   |                       |                       |                         |
   |                       |                       | **Default Value**       |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   +-----------------------+-----------------------+-------------------------+
   | write_queue_num       | Number                | **Definition**          |
   |                       |                       |                         |
   |                       |                       | Number of write queues. |
   |                       |                       |                         |
   |                       |                       | **Constraints**         |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   |                       |                       |                         |
   |                       |                       | **Range**               |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   |                       |                       |                         |
   |                       |                       | **Default Value**       |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   +-----------------------+-----------------------+-------------------------+

Example Requests
----------------

Querying details about a specified topic

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/topics/{topic}

Example Responses
-----------------

**Status code: 200**

Topic queried successfully.

.. code-block::

   {
     "name" : "topic",
     "total_read_queue_num" : 3,
     "total_write_queue_num" : 3,
     "permission" : "all",
     "brokers" : [ {
       "broker_name" : "broker-0",
       "read_queue_num" : 3,
       "write_queue_num" : 3
     } ],
     "message_type" : "NORMAL"
   }

Status Codes
------------

=========== ===========================
Status Code Description
=========== ===========================
200         Topic queried successfully.
=========== ===========================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
