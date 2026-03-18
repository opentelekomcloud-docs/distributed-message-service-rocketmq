:original_name: ShowTopicStatus.html

.. _ShowTopicStatus:

Querying the Number of Messages in a Topic
==========================================

Function
--------

This API is used to query the number of messages in a topic.

URI
---

GET /v2/{project_id}/instances/{instance_id}/topics/{topic}/status

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                         |
   +=================+=================+=================+=====================================================================================================================+
   | project_id      | Yes             | String          | **Definition**                                                                                                      |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | Project ID. For details about how to obtain it, see :ref:`Obtaining a Project ID <hrm-api-0011>`.                   |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                                     |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Range**                                                                                                           |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                                   |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------+
   | instance_id     | Yes             | String          | **Definition**                                                                                                      |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | You can call the API for querying all instances to obtain the instance ID. The instance ID is in the response body. |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                                     |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Range**                                                                                                           |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                                   |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------+
   | topic           | Yes             | String          | **Definition**                                                                                                      |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | Topic name.                                                                                                         |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                                     |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Range**                                                                                                           |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                                   |
   |                 |                 |                 |                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                 |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------------------+---------------------------------------------------------------------+-----------------------+
   | Parameter             | Type                                                                | Description           |
   +=======================+=====================================================================+=======================+
   | max_offset            | Integer                                                             | **Definition**        |
   |                       |                                                                     |                       |
   |                       |                                                                     | Maximum offset.       |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Constraints**       |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Range**             |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Default Value**     |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   +-----------------------+---------------------------------------------------------------------+-----------------------+
   | min_offset            | Integer                                                             | **Definition**        |
   |                       |                                                                     |                       |
   |                       |                                                                     | Minimum offset.       |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Constraints**       |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Range**             |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Default Value**     |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   +-----------------------+---------------------------------------------------------------------+-----------------------+
   | brokers               | Array of :ref:`brokers <showtopicstatus__response_brokers>` objects | **Definition**        |
   |                       |                                                                     |                       |
   |                       |                                                                     | Broker.               |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Constraints**       |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Range**             |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   |                       |                                                                     |                       |
   |                       |                                                                     | **Default Value**     |
   |                       |                                                                     |                       |
   |                       |                                                                     | N/A                   |
   +-----------------------+---------------------------------------------------------------------+-----------------------+

.. _showtopicstatus__response_brokers:

.. table:: **Table 3** brokers

   +-----------------------+-------------------------------------------------------------------+-----------------------+
   | Parameter             | Type                                                              | Description           |
   +=======================+===================================================================+=======================+
   | queues                | Array of :ref:`queues <showtopicstatus__response_queues>` objects | **Definition**        |
   |                       |                                                                   |                       |
   |                       |                                                                   | Queue list.           |
   |                       |                                                                   |                       |
   |                       |                                                                   | **Constraints**       |
   |                       |                                                                   |                       |
   |                       |                                                                   | N/A                   |
   |                       |                                                                   |                       |
   |                       |                                                                   | **Range**             |
   |                       |                                                                   |                       |
   |                       |                                                                   | N/A                   |
   |                       |                                                                   |                       |
   |                       |                                                                   | **Default Value**     |
   |                       |                                                                   |                       |
   |                       |                                                                   | N/A                   |
   +-----------------------+-------------------------------------------------------------------+-----------------------+
   | broker_name           | String                                                            | **Definition**        |
   |                       |                                                                   |                       |
   |                       |                                                                   | Node name.            |
   |                       |                                                                   |                       |
   |                       |                                                                   | **Constraints**       |
   |                       |                                                                   |                       |
   |                       |                                                                   | N/A                   |
   |                       |                                                                   |                       |
   |                       |                                                                   | **Range**             |
   |                       |                                                                   |                       |
   |                       |                                                                   | N/A                   |
   |                       |                                                                   |                       |
   |                       |                                                                   | **Default Value**     |
   |                       |                                                                   |                       |
   |                       |                                                                   | N/A                   |
   +-----------------------+-------------------------------------------------------------------+-----------------------+

.. _showtopicstatus__response_queues:

.. table:: **Table 4** queues

   +-----------------------+-----------------------+---------------------------+
   | Parameter             | Type                  | Description               |
   +=======================+=======================+===========================+
   | id                    | Integer               | **Definition**            |
   |                       |                       |                           |
   |                       |                       | Queue ID.                 |
   |                       |                       |                           |
   |                       |                       | **Constraints**           |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   |                       |                       |                           |
   |                       |                       | **Range**                 |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   |                       |                       |                           |
   |                       |                       | **Default Value**         |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   +-----------------------+-----------------------+---------------------------+
   | min_offset            | Integer               | **Definition**            |
   |                       |                       |                           |
   |                       |                       | Minimum offset.           |
   |                       |                       |                           |
   |                       |                       | **Constraints**           |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   |                       |                       |                           |
   |                       |                       | **Range**                 |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   |                       |                       |                           |
   |                       |                       | **Default Value**         |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   +-----------------------+-----------------------+---------------------------+
   | max_offset            | Integer               | **Definition**            |
   |                       |                       |                           |
   |                       |                       | Maximum offset.           |
   |                       |                       |                           |
   |                       |                       | **Constraints**           |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   |                       |                       |                           |
   |                       |                       | **Range**                 |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   |                       |                       |                           |
   |                       |                       | **Default Value**         |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   +-----------------------+-----------------------+---------------------------+
   | last_message_time     | Long                  | **Definition**            |
   |                       |                       |                           |
   |                       |                       | Time of the last message. |
   |                       |                       |                           |
   |                       |                       | **Constraints**           |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   |                       |                       |                           |
   |                       |                       | **Range**                 |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   |                       |                       |                           |
   |                       |                       | **Default Value**         |
   |                       |                       |                           |
   |                       |                       | N/A                       |
   +-----------------------+-----------------------+---------------------------+

Example Requests
----------------

Querying the number of messages in a specified topic

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/topics/{topic}/status

Example Responses
-----------------

**Status code: 200**

Successful

Successful.

.. code-block::

   {
     "brokers" : [ ],
     "min_offset" : 0,
     "max_offset" : 2
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         Successful
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
