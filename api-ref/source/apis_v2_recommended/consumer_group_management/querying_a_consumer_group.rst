:original_name: ShowGroup.html

.. _ShowGroup:

Querying a Consumer Group
=========================

Function
--------

This API is used to query details about a specified consumer group.

URI
---

GET /v2/{project_id}/instances/{instance_id}/groups/{group}

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
   | group           | Yes             | String          | **Definition**                                                                                                                   |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | Consumer group name.                                                                                                             |
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

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------------------+-----------------------+----------------------------------------+
   | Parameter             | Type                  | Description                            |
   +=======================+=======================+========================================+
   | enabled               | Boolean               | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Whether consumption is allowed.        |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | -  **true**: Yes                       |
   |                       |                       |                                        |
   |                       |                       | -  **false**: No                       |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+
   | broadcast             | Boolean               | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Whether to enable broadcast.           |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | -  **true**: Yes                       |
   |                       |                       |                                        |
   |                       |                       | -  **false**: No                       |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+
   | name                  | String                | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Consumer group name.                   |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+
   | group_desc            | String                | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Consumer group description.            |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+
   | created_at            | Long                  | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Creation time.                         |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+
   | retry_max_time        | Integer               | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Maximum number of retries.             |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+
   | permissions           | Array of strings      | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Permission.                            |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+
   | consume_orderly       | Boolean               | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Whether to enable orderly consumption. |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | -  **true**: Yes                       |
   |                       |                       |                                        |
   |                       |                       | -  **false**: No                       |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+
   | group_online          | Boolean               | **Definition**                         |
   |                       |                       |                                        |
   |                       |                       | Whether a consumer group is online.    |
   |                       |                       |                                        |
   |                       |                       | **Constraints**                        |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   |                       |                       |                                        |
   |                       |                       | **Range**                              |
   |                       |                       |                                        |
   |                       |                       | -  **true**: Yes                       |
   |                       |                       |                                        |
   |                       |                       | -  **false**: No                       |
   |                       |                       |                                        |
   |                       |                       | **Default Value**                      |
   |                       |                       |                                        |
   |                       |                       | N/A                                    |
   +-----------------------+-----------------------+----------------------------------------+

Example Requests
----------------

Querying details about a specified consumer group

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/groups/{group}

Example Responses
-----------------

**Status code: 200**

Consumer group queried successfully.

.. code-block::

   {
     "name" : "test",
     "group_desc" : "group_description",
     "enabled" : true,
     "broadcast" : true,
     "permissions" : [ ],
     "retry_max_time" : 10,
     "consume_orderly" : false,
     "created_at" : 1768549443385
   }

Status Codes
------------

=========== ====================================
Status Code Description
=========== ====================================
200         Consumer group queried successfully.
=========== ====================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
