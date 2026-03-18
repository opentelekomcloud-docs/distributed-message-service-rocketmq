:original_name: ListScheduledTasks.html

.. _ListScheduledTasks:

Querying the Scheduled Task List of an Instance
===============================================

Function
--------

This API is used to query the scheduled task list of an instance.

URI
---

GET /v2/{project_id}/instances/{instance_id}/scheduled-tasks

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

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                      |
   +=================+=================+=================+==================================================================================+
   | start           | No              | String          | **Definition**                                                                   |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | No. of the scheduled task to start the query.                                    |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Constraints**                                                                  |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Range**                                                                        |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Default Value**                                                                |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | limit           | No              | Integer         | **Definition**                                                                   |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | Number of scheduled tasks to be queried.                                         |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Constraints**                                                                  |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Range**                                                                        |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Default Value**                                                                |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | begin_time      | No              | String          | **Definition**                                                                   |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | Time of a scheduled task where the query starts. The format is *YYYYMMDDHHmmss*. |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Constraints**                                                                  |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Range**                                                                        |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Default Value**                                                                |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+
   | end_time        | No              | String          | **Definition**                                                                   |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | Time of a scheduled task where the query ends. The format is *YYYYMMDDHHmmss*.   |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Constraints**                                                                  |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Range**                                                                        |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | **Default Value**                                                                |
   |                 |                 |                 |                                                                                  |
   |                 |                 |                 | N/A                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+------------------------------------------------------------------------------------------------+------------------------+
   | Parameter             | Type                                                                                           | Description            |
   +=======================+================================================================================================+========================+
   | job_count             | String                                                                                         | **Definition**         |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | Total number of tasks. |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | **Constraints**        |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | N/A                    |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | **Range**              |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | N/A                    |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | **Default Value**      |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | N/A                    |
   +-----------------------+------------------------------------------------------------------------------------------------+------------------------+
   | jobs                  | Array of :ref:`ScheduledTaskEntity <listscheduledtasks__response_scheduledtaskentity>` objects | **Definition**         |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | Task list.             |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | **Constraints**        |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | N/A                    |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | **Range**              |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | N/A                    |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | **Default Value**      |
   |                       |                                                                                                |                        |
   |                       |                                                                                                | N/A                    |
   +-----------------------+------------------------------------------------------------------------------------------------+------------------------+

.. _listscheduledtasks__response_scheduledtaskentity:

.. table:: **Table 4** ScheduledTaskEntity

   +-----------------------+-----------------------+---------------------------------------------------------+
   | Parameter             | Type                  | Description                                             |
   +=======================+=======================+=========================================================+
   | id                    | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | Task ID.                                                |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+
   | name                  | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | Task name.                                              |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+
   | user_name             | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | Username.                                               |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+
   | user_id               | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | User ID.                                                |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+
   | params                | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | Task parameter.                                         |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+
   | status                | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | Task status.                                            |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | -  **CREATED**: The scheduled task is created.          |
   |                       |                       |                                                         |
   |                       |                       | -  **SUCCESS**: The scheduled task is successful.       |
   |                       |                       |                                                         |
   |                       |                       | -  **FAILED**: The scheduled task fails.                |
   |                       |                       |                                                         |
   |                       |                       | -  **DELETED**: The scheduled task is deleted.          |
   |                       |                       |                                                         |
   |                       |                       | -  **EXECUTING**: The scheduled task is being executed. |
   |                       |                       |                                                         |
   |                       |                       | -  **CANCELLED**: The scheduled task is canceled.       |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+
   | created_at            | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | Creation time.                                          |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+
   | updated_at            | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | Update time.                                            |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+
   | schedule_at           | String                | **Definition**                                          |
   |                       |                       |                                                         |
   |                       |                       | Time when a scheduled task is executed.                 |
   |                       |                       |                                                         |
   |                       |                       | **Constraints**                                         |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Range**                                               |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   |                       |                       |                                                         |
   |                       |                       | **Default Value**                                       |
   |                       |                       |                                                         |
   |                       |                       | N/A                                                     |
   +-----------------------+-----------------------+---------------------------------------------------------+

Example Requests
----------------

Querying scheduled tasks from 1970.01.01.000000 to 2024.01.01.000000 in pages

.. code-block::

   /v2/{{project_id}}/instances/{instance_id}/schedule-tasks?start=0&limit=10&beginTime=19700101000000&endTime=20240101000000

Example Responses
-----------------

**Status code: 200**

Instance's scheduled task list queried.

.. code-block::

   {
     "job_count" : 2,
     "jobs" : [ {
       "id" : "ff808082889e267601889e2df7be0013",
       "name" : "jobName",
       "user_name" : "paas_dms_03",
       "user_id" : "0b01fbb53600d4671fa8c00673c71260",
       "params" : "{\"reassignment_topics\":\"[topic-1]\"}",
       "status" : "SUCCESS",
       "created_at" : "2023-06-09T03:23:12.702Z",
       "updated_at" : "2023-06-09T03:35:00.067Z",
       "schedule_at" : "2023-06-08T05:08:26.000Z"
     } ]
   }

Status Codes
------------

=========== =======================================
Status Code Description
=========== =======================================
200         Instance's scheduled task list queried.
=========== =======================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
