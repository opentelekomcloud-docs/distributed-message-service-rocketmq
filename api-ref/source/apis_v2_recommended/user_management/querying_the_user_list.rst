:original_name: ListUser.html

.. _ListUser:

Querying the User List
======================

Function
--------

This API is used to query the user list.

URI
---

GET /v2/{project_id}/instances/{instance_id}/users

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

   +-----------+-----------+---------+-----------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type    | Description                                                                                         |
   +===========+===========+=========+=====================================================================================================+
   | limit     | No        | Integer | Number of records to query.                                                                         |
   +-----------+-----------+---------+-----------------------------------------------------------------------------------------------------+
   | offset    | No        | Integer | Offset, which is the position where the query starts. The value must be greater than or equal to 0. |
   +-----------+-----------+---------+-----------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+----------------------------------------------------------------+------------------------+
   | Parameter             | Type                                                           | Description            |
   +=======================+================================================================+========================+
   | users                 | Array of :ref:`UserResp <listuser__response_userresp>` objects | **Definition**         |
   |                       |                                                                |                        |
   |                       |                                                                | User list.             |
   |                       |                                                                |                        |
   |                       |                                                                | **Constraints**        |
   |                       |                                                                |                        |
   |                       |                                                                | N/A                    |
   |                       |                                                                |                        |
   |                       |                                                                | **Range**              |
   |                       |                                                                |                        |
   |                       |                                                                | N/A                    |
   |                       |                                                                |                        |
   |                       |                                                                | **Default Value**      |
   |                       |                                                                |                        |
   |                       |                                                                | N/A                    |
   +-----------------------+----------------------------------------------------------------+------------------------+
   | total                 | Number                                                         | **Definition**         |
   |                       |                                                                |                        |
   |                       |                                                                | Total number of users. |
   |                       |                                                                |                        |
   |                       |                                                                | **Constraints**        |
   |                       |                                                                |                        |
   |                       |                                                                | N/A                    |
   |                       |                                                                |                        |
   |                       |                                                                | **Range**              |
   |                       |                                                                |                        |
   |                       |                                                                | N/A                    |
   |                       |                                                                |                        |
   |                       |                                                                | **Default Value**      |
   |                       |                                                                |                        |
   |                       |                                                                | N/A                    |
   +-----------------------+----------------------------------------------------------------+------------------------+

.. _listuser__response_userresp:

.. table:: **Table 4** UserResp

   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+
   | Parameter             | Type                                                                 | Description                                        |
   +=======================+======================================================================+====================================================+
   | access_key            | String                                                               | **Definition**                                     |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | Username.                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Constraints**                                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Range**                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Default Value**                                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+
   | secret_key            | String                                                               | **Definition**                                     |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | Key.                                               |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Constraints**                                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Range**                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Default Value**                                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+
   | white_remote_address  | String                                                               | **Definition**                                     |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | IP address whitelist.                              |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Constraints**                                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Range**                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Default Value**                                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+
   | admin                 | Boolean                                                              | **Definition**                                     |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | Whether the user is an administrator.              |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Constraints**                                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Range**                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | -  **true**: Yes                                   |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | -  **false**: No                                   |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Default Value**                                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+
   | default_topic_perm    | String                                                               | **Definition**                                     |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | Default topic permissions.                         |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Constraints**                                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Range**                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | -  **PUB**: publish permission.                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | -  **SUB**: subscribe permission.                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | -  **PUB|SUB**: subscribe and publish permissions. |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | -  **DENY**: no permission.                        |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Default Value**                                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+
   | default_group_perm    | String                                                               | **Definition**                                     |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | Default consumer group permissions.                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Constraints**                                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Range**                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | -  **SUB**: subscribe permission.                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | -  **DENY**: no permission.                        |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Default Value**                                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+
   | topic_perms           | Array of :ref:`topic_perms <listuser__response_topic_perms>` objects | **Definition**                                     |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | Special topic permissions.                         |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Constraints**                                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Range**                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Default Value**                                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+
   | group_perms           | Array of :ref:`group_perms <listuser__response_group_perms>` objects | **Definition**                                     |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | Special consumer group permissions.                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Constraints**                                    |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Range**                                          |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | **Default Value**                                  |
   |                       |                                                                      |                                                    |
   |                       |                                                                      | N/A                                                |
   +-----------------------+----------------------------------------------------------------------+----------------------------------------------------+

.. _listuser__response_topic_perms:

.. table:: **Table 5** topic_perms

   +-----------------------+-----------------------+----------------------------------------------------+
   | Parameter             | Type                  | Description                                        |
   +=======================+=======================+====================================================+
   | name                  | String                | **Definition**                                     |
   |                       |                       |                                                    |
   |                       |                       | Topic name.                                        |
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
   | perm                  | String                | **Definition**                                     |
   |                       |                       |                                                    |
   |                       |                       | Topic permissions.                                 |
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

.. _listuser__response_group_perms:

.. table:: **Table 6** group_perms

   +-----------------------+-----------------------+-----------------------------------+
   | Parameter             | Type                  | Description                       |
   +=======================+=======================+===================================+
   | name                  | String                | **Definition**                    |
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
   | perm                  | String                | **Definition**                    |
   |                       |                       |                                   |
   |                       |                       | Consumer group permissions.       |
   |                       |                       |                                   |
   |                       |                       | **Constraints**                   |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   |                       |                       |                                   |
   |                       |                       | **Range**                         |
   |                       |                       |                                   |
   |                       |                       | -  **SUB**: subscribe permission. |
   |                       |                       |                                   |
   |                       |                       | -  **DENY**: no permission.       |
   |                       |                       |                                   |
   |                       |                       | **Default Value**                 |
   |                       |                       |                                   |
   |                       |                       | N/A                               |
   +-----------------------+-----------------------+-----------------------------------+

Example Requests
----------------

Querying the user list

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/users?offset=0&limit=10

Example Responses
-----------------

**Status code: 200**

Query result.

.. code-block::

   {
     "users" : [ {
       "access_key" : "test_01",
       "admin" : false,
       "default_group_perm" : "DENY",
       "default_topic_perm" : "SUB",
       "group_perms" : [ ],
       "secret_key" : "Abcd1234!",
       "topic_perms" : [ ],
       "white_remote_address" : ""
     } ],
     "total" : 1
   }

Status Codes
------------

=========== =============
Status Code Description
=========== =============
200         Query result.
=========== =============

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
