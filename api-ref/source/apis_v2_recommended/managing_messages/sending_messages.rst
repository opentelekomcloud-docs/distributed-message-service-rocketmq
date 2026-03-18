:original_name: SendMessageForRocketMq.html

.. _SendMessageForRocketMq:

Sending Messages
================

Function
--------

This API is used to send messages.

URI
---

POST /v2/{project_id}/rocketmq/instances/{instance_id}/messages

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

   +-----------------+-----------------+-------------------------------------------------------------------------------------------------------+-------------------+
   | Parameter       | Mandatory       | Type                                                                                                  | Description       |
   +=================+=================+=======================================================================================================+===================+
   | topic           | Yes             | String                                                                                                | **Definition**    |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | Topic name.       |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Constraints**   |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Range**         |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Default Value** |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------------+-------------------+
   | body            | Yes             | String                                                                                                | **Definition**    |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | Message content.  |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Constraints**   |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Range**         |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Default Value** |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------------+-------------------+
   | property_list   | No              | Array of :ref:`SendMessageProperties <sendmessageforrocketmq__request_sendmessageproperties>` objects | **Definition**    |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | Feature list.     |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Constraints**   |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Range**         |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | **Default Value** |
   |                 |                 |                                                                                                       |                   |
   |                 |                 |                                                                                                       | N/A               |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------------+-------------------+

.. _sendmessageforrocketmq__request_sendmessageproperties:

.. table:: **Table 3** SendMessageProperties

   +-----------------+-----------------+-----------------+-------------------+
   | Parameter       | Mandatory       | Type            | Description       |
   +=================+=================+=================+===================+
   | name            | No              | String          | **Definition**    |
   |                 |                 |                 |                   |
   |                 |                 |                 | Feature name.     |
   |                 |                 |                 |                   |
   |                 |                 |                 | **Constraints**   |
   |                 |                 |                 |                   |
   |                 |                 |                 | N/A               |
   |                 |                 |                 |                   |
   |                 |                 |                 | **Range**         |
   |                 |                 |                 |                   |
   |                 |                 |                 | N/A               |
   |                 |                 |                 |                   |
   |                 |                 |                 | **Default Value** |
   |                 |                 |                 |                   |
   |                 |                 |                 | N/A               |
   +-----------------+-----------------+-----------------+-------------------+
   | value           | No              | String          | **Definition**    |
   |                 |                 |                 |                   |
   |                 |                 |                 | Feature value.    |
   |                 |                 |                 |                   |
   |                 |                 |                 | **Constraints**   |
   |                 |                 |                 |                   |
   |                 |                 |                 | N/A               |
   |                 |                 |                 |                   |
   |                 |                 |                 | **Range**         |
   |                 |                 |                 |                   |
   |                 |                 |                 | N/A               |
   |                 |                 |                 |                   |
   |                 |                 |                 | **Default Value** |
   |                 |                 |                 |                   |
   |                 |                 |                 | N/A               |
   +-----------------+-----------------+-----------------+-------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-----------------------+--------------------------------------------------------------------------------------------------------+-----------------------+
   | Parameter             | Type                                                                                                   | Description           |
   +=======================+========================================================================================================+=======================+
   | topic                 | String                                                                                                 | **Definition**        |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | Topic name.           |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Constraints**       |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Range**             |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Default Value**     |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------+-----------------------+
   | body                  | String                                                                                                 | **Definition**        |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | Message content.      |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Constraints**       |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Range**             |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Default Value**     |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------+-----------------------+
   | property_list         | Array of :ref:`SendMessageProperties <sendmessageforrocketmq__response_sendmessageproperties>` objects | **Definition**        |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | Feature list.         |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Constraints**       |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Range**             |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Default Value**     |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------+-----------------------+
   | msg_id                | String                                                                                                 | **Definition**        |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | Message ID.           |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Constraints**       |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Range**             |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Default Value**     |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------+-----------------------+
   | queue_id              | Number                                                                                                 | **Definition**        |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | Queue ID.             |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Constraints**       |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Range**             |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Default Value**     |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------+-----------------------+
   | queue_offset          | Number                                                                                                 | **Definition**        |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | Queue offset.         |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Constraints**       |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Range**             |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Default Value**     |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------+-----------------------+
   | broker_name           | String                                                                                                 | **Definition**        |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | Broker name.          |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Constraints**       |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Range**             |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | **Default Value**     |
   |                       |                                                                                                        |                       |
   |                       |                                                                                                        | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------+-----------------------+

.. _sendmessageforrocketmq__response_sendmessageproperties:

.. table:: **Table 5** SendMessageProperties

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | name                  | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Feature name.         |
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
   | value                 | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Feature value.        |
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

Sending messages

.. code-block:: text

   POST https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/messages?topic={topic}

   {
     "topic" : "aaaaaaaaaaaa",
     "body" : "test",
     "property_list" : [ ]
   }

Example Responses
-----------------

**Status code: 200**

Queried.

.. code-block::

   {
     "topic" : "aaaaaaaaaaaa",
     "body" : "test",
     "property_list" : [ ],
     "msg_id" : "644F0E2A315323EAB33D8F4733110009",
     "queue_id" : 0,
     "queue_offset" : 0,
     "broker_name" : "broker-0"
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
