:original_name: ListConsumerGroupOfTopic.html

.. _ListConsumerGroupOfTopic:

Querying the Topic Consumer Group List
======================================

Function
--------

This API is used to query the topic consumer group list.

URI
---

GET /v2/{project_id}/instances/{instance_id}/topics/{topic}/groups

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
   | topic           | Yes             | String          | **Definition**                                                                                                                   |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | Topic name.                                                                                                                      |
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

   +-----------------+-----------------+-----------------+------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                    |
   +=================+=================+=================+================================================+
   | limit           | No              | Integer         | **Definition**                                 |
   |                 |                 |                 |                                                |
   |                 |                 |                 | Maximum number of records returned in a query. |
   |                 |                 |                 |                                                |
   |                 |                 |                 | **Constraints**                                |
   |                 |                 |                 |                                                |
   |                 |                 |                 | N/A                                            |
   |                 |                 |                 |                                                |
   |                 |                 |                 | **Range**                                      |
   |                 |                 |                 |                                                |
   |                 |                 |                 | 1-50                                           |
   |                 |                 |                 |                                                |
   |                 |                 |                 | **Default Value**                              |
   |                 |                 |                 |                                                |
   |                 |                 |                 | 10                                             |
   +-----------------+-----------------+-----------------+------------------------------------------------+
   | offset          | No              | Integer         | **Definition**                                 |
   |                 |                 |                 |                                                |
   |                 |                 |                 | Offset where the query starts.                 |
   |                 |                 |                 |                                                |
   |                 |                 |                 | **Constraints**                                |
   |                 |                 |                 |                                                |
   |                 |                 |                 | N/A                                            |
   |                 |                 |                 |                                                |
   |                 |                 |                 | **Range**                                      |
   |                 |                 |                 |                                                |
   |                 |                 |                 | >= 0                                           |
   |                 |                 |                 |                                                |
   |                 |                 |                 | **Default Value**                              |
   |                 |                 |                 |                                                |
   |                 |                 |                 | N/A                                            |
   +-----------------+-----------------+-----------------+------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | groups                | Array of strings      | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Consumer group list.  |
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

Querying the consumer group list of a specified topic

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/topics/{topic}/groups

Example Responses
-----------------

**Status code: 200**

Topic consumer group list queried successfully.

.. code-block::

   {
     "groups" : [ "CID_JODIE_1", "test_consumer" ]
   }

Status Codes
------------

=========== ===============================================
Status Code Description
=========== ===============================================
200         Topic consumer group list queried successfully.
=========== ===============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
