:original_name: ListConsumeGroupAccessPolicyForRocketMq.html

.. _ListConsumeGroupAccessPolicyForRocketMq:

Querying Users Granted Permissions for a Consumer Group
=======================================================

Function
--------

This API is used to query the list of users granted permissions for a consumer group.

URI
---

GET /v2/{project_id}/rocketmq/instances/{instance_id}/groups/{group}/accesspolicy

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
   |                 |                 |                 | Consumer group.                                                                                                                  |
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

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                             |
   +=================+=================+=================+=========================================================================================+
   | offset          | No              | Integer         | **Definition**                                                                          |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | Offset, which is the position where the query starts. The value must be no less than 0. |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | **Constraints**                                                                         |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | N/A                                                                                     |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | **Range**                                                                               |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | N/A                                                                                     |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | **Default Value**                                                                       |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | N/A                                                                                     |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+
   | limit           | No              | Integer         | **Definition**                                                                          |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | Number of records to query.                                                             |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | **Constraints**                                                                         |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | N/A                                                                                     |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | **Range**                                                                               |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | N/A                                                                                     |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | **Default Value**                                                                       |
   |                 |                 |                 |                                                                                         |
   |                 |                 |                 | N/A                                                                                     |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------------------------------------------------------------------------------+--------------------------------------+
   | Parameter             | Type                                                                                          | Description                          |
   +=======================+===============================================================================================+======================================+
   | policies              | Array of :ref:`policies <listconsumegroupaccesspolicyforrocketmq__response_policies>` objects | **Definition**                       |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | User list.                           |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Constraints**                      |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Range**                            |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Default Value**                    |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   +-----------------------+-----------------------------------------------------------------------------------------------+--------------------------------------+
   | total                 | Number                                                                                        | **Definition**                       |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | Total number of users.               |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Constraints**                      |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Range**                            |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Default Value**                    |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   +-----------------------+-----------------------------------------------------------------------------------------------+--------------------------------------+
   | name                  | String                                                                                        | **Definition**                       |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | Name of the topic or consumer group. |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Constraints**                      |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Range**                            |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | **Default Value**                    |
   |                       |                                                                                               |                                      |
   |                       |                                                                                               | N/A                                  |
   +-----------------------+-----------------------------------------------------------------------------------------------+--------------------------------------+

.. _listconsumegroupaccesspolicyforrocketmq__response_policies:

.. table:: **Table 4** policies

   +-----------------------+-----------------------+----------------------------------------------------+
   | Parameter             | Type                  | Description                                        |
   +=======================+=======================+====================================================+
   | access_key            | String                | **Definition**                                     |
   |                       |                       |                                                    |
   |                       |                       | Username.                                          |
   |                       |                       |                                                    |
   |                       |                       | **Constraints**                                    |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   |                       |                       |                                                    |
   |                       |                       | **Range**                                          |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   |                       |                       |                                                    |
   |                       |                       | **Default Value**                                  |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   +-----------------------+-----------------------+----------------------------------------------------+
   | white_remote_address  | String                | **Definition**                                     |
   |                       |                       |                                                    |
   |                       |                       | IP address whitelist.                              |
   |                       |                       |                                                    |
   |                       |                       | **Constraints**                                    |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   |                       |                       |                                                    |
   |                       |                       | **Range**                                          |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   |                       |                       |                                                    |
   |                       |                       | **Default Value**                                  |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   +-----------------------+-----------------------+----------------------------------------------------+
   | admin                 | Boolean               | **Definition**                                     |
   |                       |                       |                                                    |
   |                       |                       | Whether the user is an administrator.              |
   |                       |                       |                                                    |
   |                       |                       | **Constraints**                                    |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   |                       |                       |                                                    |
   |                       |                       | **Range**                                          |
   |                       |                       |                                                    |
   |                       |                       | -  **true**: Yes                                   |
   |                       |                       |                                                    |
   |                       |                       | -  **false**: No                                   |
   |                       |                       |                                                    |
   |                       |                       | **Default Value**                                  |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   +-----------------------+-----------------------+----------------------------------------------------+
   | perm                  | String                | **Definition**                                     |
   |                       |                       |                                                    |
   |                       |                       | User permissions.                                  |
   |                       |                       |                                                    |
   |                       |                       | **Constraints**                                    |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   |                       |                       |                                                    |
   |                       |                       | **Range**                                          |
   |                       |                       |                                                    |
   |                       |                       | -  **PUB**: publish permission.                    |
   |                       |                       |                                                    |
   |                       |                       | -  **SUB**: subscribe permission.                  |
   |                       |                       |                                                    |
   |                       |                       | -  **PUB|SUB**: subscribe and publish permissions. |
   |                       |                       |                                                    |
   |                       |                       | -  **DENY**: no permission.                        |
   |                       |                       |                                                    |
   |                       |                       | **Default Value**                                  |
   |                       |                       |                                                    |
   |                       |                       | N/A                                                |
   +-----------------------+-----------------------+----------------------------------------------------+

Example Requests
----------------

Querying the list of users granted permissions for a consumer group

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/groups/{group}/accesspolicy

Example Responses
-----------------

**Status code: 200**

List of users granted permissions for a consumer group queried.

.. code-block::

   {
     "policies" : [ {
       "access_key" : "test_01",
       "white_remote_address" : "",
       "admin" : false,
       "perm" : ""
     } ],
     "total" : 1,
     "name" : "test"
   }

Status Codes
------------

+-------------+-----------------------------------------------------------------+
| Status Code | Description                                                     |
+=============+=================================================================+
| 200         | List of users granted permissions for a consumer group queried. |
+-------------+-----------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
