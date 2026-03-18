:original_name: ListDiagnosisReportsForRocketMq.html

.. _ListDiagnosisReportsForRocketMq:

Querying an Instance Diagnosis Report List
==========================================

Function
--------

This API is used to query an instance diagnosis report list.

URI
---

GET /v2/{project_id}/rocketmq/instances/{instance_id}/diagnosis

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

   +-----------------+-----------------+-----------------+--------------------------------+
   | Parameter       | Mandatory       | Type            | Description                    |
   +=================+=================+=================+================================+
   | offset          | No              | Integer         | **Definition**                 |
   |                 |                 |                 |                                |
   |                 |                 |                 | Offset where the query starts. |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Constraints**                |
   |                 |                 |                 |                                |
   |                 |                 |                 | N/A                            |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Range**                      |
   |                 |                 |                 |                                |
   |                 |                 |                 | >= 0                           |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Default Value**              |
   |                 |                 |                 |                                |
   |                 |                 |                 | N/A                            |
   +-----------------+-----------------+-----------------+--------------------------------+
   | limit           | No              | Integer         | **Definition**                 |
   |                 |                 |                 |                                |
   |                 |                 |                 | Number of records to query.    |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Constraints**                |
   |                 |                 |                 |                                |
   |                 |                 |                 | N/A                            |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Range**                      |
   |                 |                 |                 |                                |
   |                 |                 |                 | N/A                            |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Default Value**              |
   |                 |                 |                 |                                |
   |                 |                 |                 | N/A                            |
   +-----------------+-----------------+-----------------+--------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-------------------------------------------------------------------------------------------------------------+------------------------+
   | Parameter             | Type                                                                                                        | Description            |
   +=======================+=============================================================================================================+========================+
   | diagnosis_report_list | Array of :ref:`DiagnosisReportResp <listdiagnosisreportsforrocketmq__response_diagnosisreportresp>` objects | **Definition**         |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | Diagnosis report list. |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | **Constraints**        |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | N/A                    |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | **Range**              |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | N/A                    |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | **Default Value**      |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | N/A                    |
   +-----------------------+-------------------------------------------------------------------------------------------------------------+------------------------+
   | total_num             | AnyType                                                                                                     | **Definition**         |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | Number of reports.     |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | **Constraints**        |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | N/A                    |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | **Range**              |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | N/A                    |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | **Default Value**      |
   |                       |                                                                                                             |                        |
   |                       |                                                                                                             | N/A                    |
   +-----------------------+-------------------------------------------------------------------------------------------------------------+------------------------+

.. _listdiagnosisreportsforrocketmq__response_diagnosisreportresp:

.. table:: **Table 4** DiagnosisReportResp

   +-----------------------+-----------------------+-----------------------------------+
   | Parameter             | Type                  | Description                       |
   +=======================+=======================+===================================+
   | report_id             | String                | **Definition**                    |
   |                       |                       |                                   |
   |                       |                       | Report ID.                        |
   |                       |                       |                                   |
   |                       |                       | **Constraints**                   |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Range**                         |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Default Value**                 |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   +-----------------------+-----------------------+-----------------------------------+
   | group_name            | String                | **Definition**                    |
   |                       |                       |                                   |
   |                       |                       | Consumer group name.              |
   |                       |                       |                                   |
   |                       |                       | **Constraints**                   |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Range**                         |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Default Value**                 |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   +-----------------------+-----------------------+-----------------------------------+
   | consumer_nums         | Integer               | **Definition**                    |
   |                       |                       |                                   |
   |                       |                       | Number of consumers.              |
   |                       |                       |                                   |
   |                       |                       | **Constraints**                   |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Range**                         |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Default Value**                 |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   +-----------------------+-----------------------+-----------------------------------+
   | status                | String                | **Definition**                    |
   |                       |                       |                                   |
   |                       |                       | Status.                           |
   |                       |                       |                                   |
   |                       |                       | **Constraints**                   |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Range**                         |
   |                       |                       |                                   |
   |                       |                       | -  **diagnosing**                 |
   |                       |                       |                                   |
   |                       |                       | -  **failed**                     |
   |                       |                       |                                   |
   |                       |                       | -  **deleted** (manually)         |
   |                       |                       |                                   |
   |                       |                       | -  **finished**                   |
   |                       |                       |                                   |
   |                       |                       | -  **normal**: No problems found. |
   |                       |                       |                                   |
   |                       |                       | -  **abnormal**: Problems found.  |
   |                       |                       |                                   |
   |                       |                       | **Default Value**                 |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   +-----------------------+-----------------------+-----------------------------------+
   | created_at            | String                | **Definition**                    |
   |                       |                       |                                   |
   |                       |                       | Creation time.                    |
   |                       |                       |                                   |
   |                       |                       | **Constraints**                   |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Range**                         |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Default Value**                 |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   +-----------------------+-----------------------+-----------------------------------+
   | abnormal_item_sum     | Integer               | **Definition**                    |
   |                       |                       |                                   |
   |                       |                       | Number of abnormal items.         |
   |                       |                       |                                   |
   |                       |                       | **Constraints**                   |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Range**                         |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Default Value**                 |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   +-----------------------+-----------------------+-----------------------------------+
   | faulted_node_sum      | Integer               | **Definition**                    |
   |                       |                       |                                   |
   |                       |                       | Number of abnormal nodes.         |
   |                       |                       |                                   |
   |                       |                       | **Constraints**                   |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Range**                         |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Default Value**                 |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   +-----------------------+-----------------------+-----------------------------------+

Example Requests
----------------

Querying an instance diagnosis report list

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/diagnosis

Example Responses
-----------------

**Status code: 200**

success

.. code-block::

   {
     "diagnosis_report_list" : {
       "report_id" : "b00a070e-75e0-4463-b53e-fbc29dcff951",
       "status" : "finished",
       "group_name" : "test",
       "created_at" : "2025-05-28 11:25:58.477",
       "abnormal_item_sum" : 0,
       "faulted_node_sum" : 0
     },
     "total_num" : 1
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
