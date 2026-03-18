:original_name: BatchDeleteRocketMqMigrationTask.html

.. _BatchDeleteRocketMqMigrationTask:

Deleting Metadata Migration Tasks in Batches
============================================

Function
--------

This API is used to delete metadata migration tasks in batches.

URI
---

POST /v2/{project_id}/instances/{instance_id}/metadata/batch-delete

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
   | task_ids        | Yes             | Array of strings | **Definition**       |
   |                 |                 |                  |                      |
   |                 |                 |                  | Tasks to be deleted. |
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

   +-----------------------+-----------------------+----------------------------------------------+
   | Parameter             | Type                  | Description                                  |
   +=======================+=======================+==============================================+
   | success_task_list     | Array of strings      | **Definition**                               |
   |                       |                       |                                              |
   |                       |                       | List of tasks that are successfully deleted. |
   |                       |                       |                                              |
   |                       |                       | **Constraints**                              |
   |                       |                       |                                              |
   |                       |                       | N/A                                          |
   |                       |                       |                                              |
   |                       |                       | **Range**                                    |
   |                       |                       |                                              |
   |                       |                       | N/A                                          |
   |                       |                       |                                              |
   |                       |                       | **Default Value**                            |
   |                       |                       |                                              |
   |                       |                       | N/A                                          |
   +-----------------------+-----------------------+----------------------------------------------+

Example Requests
----------------

Deleting metadata migration tasks in batches

.. code-block:: text

   POST https://{endpoint}/v2/{project_id}/instances/{instance_id}/metadata/batch-delete

   {
     "task_ids" : [ "1b8f2c93-8057-4bdd-9be5-5b6883737099", "fa89699b-61b9-497d-b1ac-972623f3c0ce" ]
   }

Example Responses
-----------------

**Status code: 200**

Metadata migration tasks deleted in batches.

.. code-block::

   {
     "success_task_list" : [ "1b8f2c93-8057-4bdd-9be5-5b6883737099", "fa89699b-61b9-497d-b1ac-972623f3c0ce" ]
   }

Status Codes
------------

=========== ============================================
Status Code Description
=========== ============================================
200         Metadata migration tasks deleted in batches.
=========== ============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
