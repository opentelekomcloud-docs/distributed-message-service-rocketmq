:original_name: ListRocketMqMigrationTask.html

.. _ListRocketMqMigrationTask:

Querying All Migration Tasks or a Specified Migration Task of an Instance
=========================================================================

Function
--------

This API is used to query all migration tasks or a specified migration task of an instance.

URI
---

GET /v2/{project_id}/instances/{instance_id}/metadata

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

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                         |
   +=================+=================+=================+=====================================================================================================================================================+
   | id              | No              | String          | **Definition**                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | Task ID.                                                                                                                                            |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Range**                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | type            | No              | String          | **Definition**                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | Query type.                                                                                                                                         |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Range**                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | -  **vhost**: virtual host                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | -  **exchange**                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | -  **queue**                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | -  **all**                                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | Integer         | **Definition**                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | Current page, starting from 1.                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Range**                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | Integer         | **Definition**                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | Current page size.                                                                                                                                  |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Range**                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | name            | No              | String          | **Definition**                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | Virtual host name.                                                                                                                                  |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | -  When the vhost list is queried, this field can be left empty.                                                                                    |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | -  When the exchange list is queried, set this field to the name of the vhost to which the exchange belongs.                                        |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | -  When the queue list is queried, set this field to *vhost of the queue's exchange*\ ``-``\ *queue's exchange*, for example, **vhost1-exchange1**. |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Range**                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                     |
   |                 |                 |                 | N/A                                                                                                                                                 |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------------------------------------------------------------------------+-------------------------------------------+
   | Parameter             | Type                                                                                    | Description                               |
   +=======================+=========================================================================================+===========================================+
   | total                 | Integer                                                                                 | **Definition**                            |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | Total number of metadata migration tasks. |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | **Constraints**                           |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | N/A                                       |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | **Range**                                 |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | N/A                                       |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | **Default Value**                         |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | N/A                                       |
   +-----------------------+-----------------------------------------------------------------------------------------+-------------------------------------------+
   | task                  | Array of :ref:`MetadataTask <listrocketmqmigrationtask__response_metadatatask>` objects | **Definition**                            |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | List of metadata migration tasks.         |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | **Constraints**                           |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | N/A                                       |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | **Range**                                 |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | N/A                                       |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | **Default Value**                         |
   |                       |                                                                                         |                                           |
   |                       |                                                                                         | N/A                                       |
   +-----------------------+-----------------------------------------------------------------------------------------+-------------------------------------------+

.. _listrocketmqmigrationtask__response_metadatatask:

.. table:: **Table 4** MetadataTask

   +-----------------------+-----------------------+---------------------------------------------------+
   | Parameter             | Type                  | Description                                       |
   +=======================+=======================+===================================================+
   | id                    | String                | **Definition**                                    |
   |                       |                       |                                                   |
   |                       |                       | ID of a metadata migration task.                  |
   |                       |                       |                                                   |
   |                       |                       | **Constraints**                                   |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   |                       |                       |                                                   |
   |                       |                       | **Range**                                         |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   |                       |                       |                                                   |
   |                       |                       | **Default Value**                                 |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   +-----------------------+-----------------------+---------------------------------------------------+
   | name                  | String                | **Definition**                                    |
   |                       |                       |                                                   |
   |                       |                       | Name of a metadata migration task.                |
   |                       |                       |                                                   |
   |                       |                       | **Constraints**                                   |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   |                       |                       |                                                   |
   |                       |                       | **Range**                                         |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   |                       |                       |                                                   |
   |                       |                       | **Default Value**                                 |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   +-----------------------+-----------------------+---------------------------------------------------+
   | start_date            | String                | **Definition**                                    |
   |                       |                       |                                                   |
   |                       |                       | Start time of a metadata migration task.          |
   |                       |                       |                                                   |
   |                       |                       | **Constraints**                                   |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   |                       |                       |                                                   |
   |                       |                       | **Range**                                         |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   |                       |                       |                                                   |
   |                       |                       | **Default Value**                                 |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   +-----------------------+-----------------------+---------------------------------------------------+
   | status                | String                | **Definition**                                    |
   |                       |                       |                                                   |
   |                       |                       | Status of a metadata migration task.              |
   |                       |                       |                                                   |
   |                       |                       | **Constraints**                                   |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   |                       |                       |                                                   |
   |                       |                       | **Range**                                         |
   |                       |                       |                                                   |
   |                       |                       | -  **creating**                                   |
   |                       |                       |                                                   |
   |                       |                       | -  **starting**: The migration is in progress.    |
   |                       |                       |                                                   |
   |                       |                       | -  **failed**                                     |
   |                       |                       |                                                   |
   |                       |                       | -  **finished**                                   |
   |                       |                       |                                                   |
   |                       |                       | **Default Value**                                 |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   +-----------------------+-----------------------+---------------------------------------------------+
   | type                  | String                | **Definition**                                    |
   |                       |                       |                                                   |
   |                       |                       | Metadata migration type.                          |
   |                       |                       |                                                   |
   |                       |                       | **Constraints**                                   |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   |                       |                       |                                                   |
   |                       |                       | **Range**                                         |
   |                       |                       |                                                   |
   |                       |                       | -  **rocketmq**: from RocketMQ to RocketMQ.       |
   |                       |                       |                                                   |
   |                       |                       | -  **rabbitToRocket**: from RabbitMQ to RocketMQ. |
   |                       |                       |                                                   |
   |                       |                       | **Default Value**                                 |
   |                       |                       |                                                   |
   |                       |                       | N/A                                               |
   +-----------------------+-----------------------+---------------------------------------------------+

Example Requests
----------------

Querying all migration tasks of a RocketMQ instance

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/metadata

Example Responses
-----------------

**Status code: 200**

Returned status code.

.. code-block::

   {
     "total" : 1,
     "task" : [ {
       "id" : "6cf4dcd3-8471-4139-8b5b-8a3a71f704c7",
       "name" : "task-932331847",
       "start_date" : "2023-03-13 19:43:32.12",
       "status" : "finished",
       "type" : "rabbitToRocket"
     } ]
   }

Status Codes
------------

=========== =====================
Status Code Description
=========== =====================
200         Returned status code.
=========== =====================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
