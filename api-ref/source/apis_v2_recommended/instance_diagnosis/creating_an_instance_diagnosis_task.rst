:original_name: CreateDiagnosisTaskForRocketMq.html

.. _CreateDiagnosisTaskForRocketMq:

Creating an Instance Diagnosis Task
===================================

Function
--------

This API is used to create an instance diagnosis task.

URI
---

POST /v2/{project_id}/rocketmq/instances/{instance_id}/diagnosis

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

   +-----------------+-----------------+------------------+----------------------+
   | Parameter       | Mandatory       | Type             | Description          |
   +=================+=================+==================+======================+
   | group_name      | Yes             | String           | **Definition**       |
   |                 |                 |                  |                      |
   |                 |                 |                  | Consumer group name. |
   |                 |                 |                  |                      |
   |                 |                 |                  | **Constraints**      |
   |                 |                 |                  |                      |
   |                 |                 |                  | N/A                  |
   |                 |                 |                  |                      |
   |                 |                 |                  | **Range**            |
   |                 |                 |                  |                      |
   |                 |                 |                  | N/A                  |
   |                 |                 |                  |                      |
   |                 |                 |                  | **Default Value**    |
   |                 |                 |                  |                      |
   |                 |                 |                  | N/A                  |
   +-----------------+-----------------+------------------+----------------------+
   | node_id_list    | No              | Array of strings | **Definition**       |
   |                 |                 |                  |                      |
   |                 |                 |                  | Node ID list.        |
   |                 |                 |                  |                      |
   |                 |                 |                  | **Constraints**      |
   |                 |                 |                  |                      |
   |                 |                 |                  | N/A                  |
   |                 |                 |                  |                      |
   |                 |                 |                  | **Range**            |
   |                 |                 |                  |                      |
   |                 |                 |                  | N/A                  |
   |                 |                 |                  |                      |
   |                 |                 |                  | **Default Value**    |
   |                 |                 |                  |                      |
   |                 |                 |                  | N/A                  |
   +-----------------+-----------------+------------------+----------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | report_id             | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Report ID.            |
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

Creating an instance diagnosis task

.. code-block:: text

   POST https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/diagnosis

   {
     "group_name" : "test",
     "node_id_list" : [ ]
   }

Example Responses
-----------------

**Status code: 200**

success

.. code-block::

   {
     "report_id" : "b00a070e-75e0-4463-b53e-fbc29dcff951"
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         success
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
