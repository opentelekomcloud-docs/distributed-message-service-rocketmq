:original_name: BatchDeleteDiagnosisRecordsForRocketMq.html

.. _BatchDeleteDiagnosisRecordsForRocketMq:

Deleting Instance Diagnosis Reports in Batches
==============================================

Function
--------

This API is used to delete diagnosis reports of an instance in batches.

URI
---

POST /v2/{project_id}/rocketmq/instances/{instance_id}/diagnosis/batch-delete

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                      |
   +=================+=================+=================+==================================================================================================================================+
   | project_id      | Yes             | String          | **Definition**                                                                                                                   |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | Project ID. For details, see :ref:`Obtaining a Project ID <hrm-api-0011>`.                                                       |
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

   +-----------------+-----------------+------------------+---------------------------+
   | Parameter       | Mandatory       | Type             | Description               |
   +=================+=================+==================+===========================+
   | report_id_list  | No              | Array of strings | **Definition**:           |
   |                 |                 |                  |                           |
   |                 |                 |                  | Diagnosis report ID list. |
   |                 |                 |                  |                           |
   |                 |                 |                  | **Constraints**:          |
   |                 |                 |                  |                           |
   |                 |                 |                  | N/A                       |
   |                 |                 |                  |                           |
   |                 |                 |                  | **Range**:                |
   |                 |                 |                  |                           |
   |                 |                 |                  | N/A                       |
   |                 |                 |                  |                           |
   |                 |                 |                  | **Default Value**:        |
   |                 |                 |                  |                           |
   |                 |                 |                  | N/A                       |
   +-----------------+-----------------+------------------+---------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------+---------------------------+
   | Parameter             | Type                  | Description               |
   +=======================+=======================+===========================+
   | report_id_list        | Array of strings      | **Definition**            |
   |                       |                       |                           |
   |                       |                       | Diagnosis report ID list. |
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

Deleting diagnosis reports of an instance in batches

.. code-block:: text

   POST https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/diagnosis/batch-delete

   {
     "report_id_list" : [ "a68bb70a-ac92-4047-b8a6-30612b521624" ]
   }

Example Responses
-----------------

**Status code: 200**

success

.. code-block::

   {
     "report_id_list" : [ "a68bb70a-ac92-4047-b8a6-30612b521624" ]
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
