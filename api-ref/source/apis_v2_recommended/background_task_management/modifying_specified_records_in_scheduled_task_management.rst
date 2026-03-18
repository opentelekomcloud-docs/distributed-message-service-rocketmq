:original_name: UpdateScheduledTask.html

.. _UpdateScheduledTask:

Modifying Specified Records in Scheduled Task Management
========================================================

Function
--------

This API is used to modify specified records in scheduled task management.

URI
---

PUT /v2/{project_id}/instances/{instance_id}/scheduled-tasks/{task_id}

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
   | task_id         | Yes             | String          | **Definition**                                                                                                                   |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | Scheduled task ID.                                                                                                               |
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

   +-----------------+-----------------+-----------------+--------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                      |
   +=================+=================+=================+==================================================+
   | execute_at      | No              | String          | **Definition**                                   |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | Modifies the execution time of a scheduled task. |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | **Constraints**                                  |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | N/A                                              |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | **Range**                                        |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | N/A                                              |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | **Default Value**                                |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | N/A                                              |
   +-----------------+-----------------+-----------------+--------------------------------------------------+
   | status          | No              | String          | **Definition**                                   |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | Modifies the status of a scheduled task.         |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | **Constraints**                                  |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | N/A                                              |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | **Range**                                        |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | -  **CANCELLED**                                 |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | **Default Value**                                |
   |                 |                 |                 |                                                  |
   |                 |                 |                 | N/A                                              |
   +-----------------+-----------------+-----------------+--------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 204**

Scheduled task modified.

None

Example Requests
----------------

-  Modifying the execution time to 20240101000000 for a specified scheduled task

   .. code-block::

      /v2/{project_id}/instances/{instance_id}/scheduled-tasks/{task_id}?execute_at=20240101000000

-  Canceling a specified scheduled task

   .. code-block::

      /v2/{project_id}/instances/{instance_id}/scheduled-tasks/{task_id}?status=CANCELLED

Example Responses
-----------------

None

Status Codes
------------

=========== ========================
Status Code Description
=========== ========================
204         Scheduled task modified.
=========== ========================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
