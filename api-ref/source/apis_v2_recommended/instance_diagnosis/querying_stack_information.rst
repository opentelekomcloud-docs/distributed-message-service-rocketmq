:original_name: ShowDiagnosisStackForRocketMq.html

.. _ShowDiagnosisStackForRocketMq:

Querying Stack Information
==========================

Function
--------

This API is used to query stack information.

URI
---

GET /v2/{project_id}/rocketmq/diagnosis/stack/{stack_id}

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                       |
   +=================+=================+=================+===================================================================================================+
   | project_id      | Yes             | String          | **Definition**                                                                                    |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | Project ID. For details about how to obtain it, see :ref:`Obtaining a Project ID <hrm-api-0011>`. |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | **Constraints**                                                                                   |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | N/A                                                                                               |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | **Range**                                                                                         |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | N/A                                                                                               |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | **Default Value**                                                                                 |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | N/A                                                                                               |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | stack_id        | Yes             | String          | **Definition**                                                                                    |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | Stack ID. It is obtained from the API for querying an instance diagnosis report.                  |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | **Constraints**                                                                                   |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | N/A                                                                                               |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | **Range**                                                                                         |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | N/A                                                                                               |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | **Default Value**                                                                                 |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | N/A                                                                                               |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------------------+-----------------------+----------------------------------+
   | Parameter             | Type                  | Description                      |
   +=======================+=======================+==================================+
   | thread_name           | String                | **Definition**                   |
   |                       |                       |                                  |
   |                       |                       | Thread name.                     |
   |                       |                       |                                  |
   |                       |                       | **Constraints**                  |
   |                       |                       |                                  |
   |                       |                       | N/A                              |
   |                       |                       |                                  |
   |                       |                       | **Range**                        |
   |                       |                       |                                  |
   |                       |                       | N/A                              |
   |                       |                       |                                  |
   |                       |                       | **Default Value**                |
   |                       |                       |                                  |
   |                       |                       | N/A                              |
   +-----------------------+-----------------------+----------------------------------+
   | stack                 | String                | **Definition**                   |
   |                       |                       |                                  |
   |                       |                       | Stack information of the client. |
   |                       |                       |                                  |
   |                       |                       | **Constraints**                  |
   |                       |                       |                                  |
   |                       |                       | N/A                              |
   |                       |                       |                                  |
   |                       |                       | **Range**                        |
   |                       |                       |                                  |
   |                       |                       | N/A                              |
   |                       |                       |                                  |
   |                       |                       | **Default Value**                |
   |                       |                       |                                  |
   |                       |                       | N/A                              |
   +-----------------------+-----------------------+----------------------------------+

Example Requests
----------------

Querying stack information

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/rocketmq/diagnosis/stack/{stack_id}

Example Responses
-----------------

**Status code: 200**

success

.. code-block::

   {
     "thread_name" : "name",
     "stack" : "xxxxxxxxxxxxxxxx"
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
