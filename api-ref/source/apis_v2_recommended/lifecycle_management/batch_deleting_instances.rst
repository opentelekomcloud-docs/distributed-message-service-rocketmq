:original_name: BatchDeleteInstances.html

.. _BatchDeleteInstances:

Batch Deleting Instances
========================

Function
--------

This API is used to delete instances in batches. **Data in the instances will be deleted without any backup. Exercise caution when performing this operation.**

URI
---

POST /v2/{project_id}/instances/action

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

Request Parameters
------------------

.. table:: **Table 2** Request body parameters

   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                                                |
   +=================+=================+==================+============================================================================================================================+
   | instances       | No              | Array of strings | **Definition**                                                                                                             |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | List of instance IDs.                                                                                                      |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Constraints**                                                                                                            |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Range**                                                                                                                  |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Default Value**                                                                                                          |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------+
   | action          | Yes             | String           | **Definition**                                                                                                             |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | Operation to be performed on instances. Value: **delete**.                                                                 |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Constraints**                                                                                                            |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Range**                                                                                                                  |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | -  **delete**                                                                                                              |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Default Value**                                                                                                          |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------+
   | all_failure     | No              | String           | **Definition**                                                                                                             |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | When set to **reliability**, this parameter indicates that all RocketMQ instances that fail to be created will be deleted. |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Constraints**                                                                                                            |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Range**                                                                                                                  |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | -  **reliability**                                                                                                         |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Default Value**                                                                                                          |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------+
   | force_delete    | No              | Boolean          | **Definition**                                                                                                             |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | Whether to forcibly delete.                                                                                                |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Constraints**                                                                                                            |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Range**                                                                                                                  |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | -  **true**: Yes, forcibly deleted instances are not moved to the recycle bin.                                             |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | -  **false**: No, instances will be moved to the recycle bin after the recycle bin function is enabled.                    |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | **Default Value**                                                                                                          |
   |                 |                 |                  |                                                                                                                            |
   |                 |                 |                  | N/A                                                                                                                        |
   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+--------------------------------------------------------------------------+----------------------------------+
   | Parameter             | Type                                                                     | Description                      |
   +=======================+==========================================================================+==================================+
   | results               | Array of :ref:`results <batchdeleteinstances__response_results>` objects | **Definition**                   |
   |                       |                                                                          |                                  |
   |                       |                                                                          | Result of instance modification. |
   |                       |                                                                          |                                  |
   |                       |                                                                          | **Constraints**                  |
   |                       |                                                                          |                                  |
   |                       |                                                                          | N/A                              |
   |                       |                                                                          |                                  |
   |                       |                                                                          | **Range**                        |
   |                       |                                                                          |                                  |
   |                       |                                                                          | N/A                              |
   |                       |                                                                          |                                  |
   |                       |                                                                          | **Default Value**                |
   |                       |                                                                          |                                  |
   |                       |                                                                          | N/A                              |
   +-----------------------+--------------------------------------------------------------------------+----------------------------------+

.. _batchdeleteinstances__response_results:

.. table:: **Table 4** results

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | result                | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Operation result.     |
   |                       |                       |                       |
   |                       |                       | **Constraints**       |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   |                       |                       |                       |
   |                       |                       | **Range**             |
   |                       |                       |                       |
   |                       |                       | -  **success**        |
   |                       |                       |                       |
   |                       |                       | -  **failed**         |
   |                       |                       |                       |
   |                       |                       | **Default Value**     |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   +-----------------------+-----------------------+-----------------------+
   | instance              | String                | Instance ID.          |
   +-----------------------+-----------------------+-----------------------+

**Status code: 204**

RocketMQ instance creation failures deleted.

Example Requests
----------------

-  Batch deleting RocketMQ instances

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/instances/action

      {
        "action" : "delete",
        "instances" : [ "54602a9d-5e22-4239-9123-77e350df4a34", "7166cdea-dbad-4d79-9610-7163e6f8b640" ]
      }

-  Deleting all RocketMQ instances that fail to be created

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/instances/action

      {
        "action" : "delete",
        "all_failure" : "reliability"
      }

Example Responses
-----------------

**Status code: 200**

Instances deleted.

.. code-block::

   {
     "results" : [ {
       "result" : "success",
       "instance" : "019cacb7-4ff0-4d3c-9f33-f5f7b7fdc0e6"
     } ]
   }

Status Codes
------------

=========== ============================================
Status Code Description
=========== ============================================
200         Instances deleted.
204         RocketMQ instance creation failures deleted.
=========== ============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
