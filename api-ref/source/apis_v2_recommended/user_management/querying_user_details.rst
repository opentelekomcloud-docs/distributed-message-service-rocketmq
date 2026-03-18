:original_name: ShowUser.html

.. _ShowUser:

Querying User Details
=====================

Function
--------

This API is used to query user details.

URI
---

GET /v2/{project_id}/instances/{instance_id}/users/{user_name}

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
   | user_name       | Yes             | String          | **Definition**                                                                                                                   |
   |                 |                 |                 |                                                                                                                                  |
   |                 |                 |                 | Username.                                                                                                                        |
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
   | topic_perms           | Array of :ref:`topic_perms <showuser__response_topic_perms>` objects | **Definition**                                     |
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
   | group_perms           | Array of :ref:`group_perms <showuser__response_group_perms>` objects | **Definition**                                     |
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

.. _showuser__response_topic_perms:

.. table:: **Table 3** topic_perms

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

.. _showuser__response_group_perms:

.. table:: **Table 4** group_perms

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

Querying user details

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/users/{user_name}

Example Responses
-----------------

**Status code: 200**

User details queried successfully.

.. code-block::

   {
     "access_key" : "test_01",
     "admin" : false,
     "default_group_perm" : "DENY",
     "default_topic_perm" : "SUB",
     "group_perms" : [ ],
     "secret_key" : "Abcd1234!",
     "topic_perms" : [ ],
     "white_remote_address" : ""
   }

Status Codes
------------

=========== ==================================
Status Code Description
=========== ==================================
200         User details queried successfully.
=========== ==================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
