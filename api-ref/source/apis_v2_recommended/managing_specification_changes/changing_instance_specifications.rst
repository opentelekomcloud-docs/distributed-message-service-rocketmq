:original_name: ResizeInstanceForRocketMq.html

.. _ResizeInstanceForRocketMq:

Changing Instance Specifications
================================

Function
--------

This API is used to change instance specifications.

URI
---

POST /v2/{project_id}/rocketmq/instances/{instance_id}/extend

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

   +-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter         | Mandatory       | Type            | Description                                                                                                                                                 |
   +===================+=================+=================+=============================================================================================================================================================+
   | oper_type         | Yes             | String          | **Definition**                                                                                                                                              |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | Change type.                                                                                                                                                |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Constraints**                                                                                                                                             |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | N/A                                                                                                                                                         |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Range**                                                                                                                                                   |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | -  **storage**: Expand the storage without changing the broker quantity.                                                                                    |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | -  **horizontal**: Scale up the RocketMQ 5.x instance specification.                                                                                        |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Default Value**                                                                                                                                           |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | N/A                                                                                                                                                         |
   +-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | new_storage_space | No              | Integer         | **Definition**                                                                                                                                              |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | New storage specification                                                                                                                                   |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Constraints**                                                                                                                                             |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | This parameter is valid and mandatory when **oper_type** is set to **storage**.                                                                             |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | -  If **oper_type** is set to **storage**, the storage space of each broker must be expanded by at least 100 GB.                                            |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | -  If **oper_type** is set to **horizontal**, the storage space of each broker remains unchanged.                                                           |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Range**                                                                                                                                                   |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | N/A                                                                                                                                                         |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Default Value**                                                                                                                                           |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | N/A                                                                                                                                                         |
   +-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | new_product_id    | No              | String          | **Definition**                                                                                                                                              |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | New product ID                                                                                                                                              |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Constraints**                                                                                                                                             |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | -  For RocketMQ 5.x: this parameter is valid and mandatory if **oper_type** is set to **horizontal**. Specification changes are only for cluster instances. |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Range**                                                                                                                                                   |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | N/A                                                                                                                                                         |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Default Value**                                                                                                                                           |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | N/A                                                                                                                                                         |
   +-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | publicip_id       | No              | String          | **Definition**                                                                                                                                              |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | ID of the EIP bound to the instance. Use commas (,) to separate multiple EIP IDs.                                                                           |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Constraints**                                                                                                                                             |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | This parameter is mandatory when **oper_type** is **horizontal** and public access is enabled.                                                              |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Range**                                                                                                                                                   |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | N/A                                                                                                                                                         |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | **Default Value**                                                                                                                                           |
   |                   |                 |                 |                                                                                                                                                             |
   |                   |                 |                 | N/A                                                                                                                                                         |
   +-------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------+--------------------------------------------+
   | Parameter             | Type                  | Description                                |
   +=======================+=======================+============================================+
   | job_id                | String                | **Definition**                             |
   |                       |                       |                                            |
   |                       |                       | ID of the specification modification task. |
   |                       |                       |                                            |
   |                       |                       | **Constraints**                            |
   |                       |                       |                                            |
   |                       |                       | N/A                                        |
   |                       |                       |                                            |
   |                       |                       | **Range**                                  |
   |                       |                       |                                            |
   |                       |                       | N/A                                        |
   |                       |                       |                                            |
   |                       |                       | **Default Value**                          |
   |                       |                       |                                            |
   |                       |                       | N/A                                        |
   +-----------------------+-----------------------+--------------------------------------------+

Example Requests
----------------

-  Increasing an instance flavor

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/extend

      {
        "oper_type" : "horizontal",
        "new_product_id" : "rocketmq.b2.large.4",
        "new_storage_space" : 1200
      }

-  Expanding instance storage

   .. code-block:: text

      POST https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/extend

      {
        "oper_type" : "storage",
        "new_storage_space" : 300
      }

Example Responses
-----------------

**Status code: 200**

Instance specifications changed.

.. code-block::

   {
     "job_id" : "93b94287-728d-4bb1-a158-cb66cb0854e7"
   }

Status Codes
------------

=========== ================================
Status Code Description
=========== ================================
200         Instance specifications changed.
=========== ================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
