:original_name: ShowQuotas.html

.. _ShowQuotas:

Querying Tenant Quotas
======================

Function
--------

This API is used to query the maximum number of instances that a tenant can create, the number of created instances, and the maximum number of tags that can be created for each instance.

URI
---

GET /v2/{project_id}/quotas

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

.. table:: **Table 2** Query Parameters

   +------------------+-----------------+-----------------+----------------------------------------------------+
   | Parameter        | Mandatory       | Type            | Description                                        |
   +==================+=================+=================+====================================================+
   | includeTagsQuota | No              | String          | **Definition**                                     |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | Whether a tag quota flag is included.              |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | **Constraints**                                    |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | N/A                                                |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | **Range**                                          |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | -  **true**: Yes                                   |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | -  **false**: No                                   |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | **Default Value**                                  |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | true                                               |
   +------------------+-----------------+-----------------+----------------------------------------------------+
   | onlyQuota        | No              | String          | **Definition**                                     |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | Queries a specified quota engine.                  |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | **Constraints**                                    |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | N/A                                                |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | **Range**                                          |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | -  **reliability**: RocketMQ message engine alias. |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | -  **kafka**: Kafka message engine alias.          |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | **Default Value**                                  |
   |                  |                 |                 |                                                    |
   |                  |                 |                 | N/A                                                |
   +------------------+-----------------+-----------------+----------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+----------------------------------------------------+-----------------------+
   | Parameter             | Type                                               | Description           |
   +=======================+====================================================+=======================+
   | quotas                | :ref:`quotas <showquotas__response_quotas>` object | **Definition**        |
   |                       |                                                    |                       |
   |                       |                                                    | Quota information.    |
   |                       |                                                    |                       |
   |                       |                                                    | **Constraints**       |
   |                       |                                                    |                       |
   |                       |                                                    | N/A                   |
   |                       |                                                    |                       |
   |                       |                                                    | **Range**             |
   |                       |                                                    |                       |
   |                       |                                                    | N/A                   |
   |                       |                                                    |                       |
   |                       |                                                    | **Default Value**     |
   |                       |                                                    |                       |
   |                       |                                                    | N/A                   |
   +-----------------------+----------------------------------------------------+-----------------------+

.. _showquotas__response_quotas:

.. table:: **Table 4** quotas

   +-----------------------+----------------------------------------------------------------------------------------+-----------------------+
   | Parameter             | Type                                                                                   | Description           |
   +=======================+========================================================================================+=======================+
   | resources             | Array of :ref:`QuotaResourceEntity <showquotas__response_quotaresourceentity>` objects | **Definition**        |
   |                       |                                                                                        |                       |
   |                       |                                                                                        | Quota list.           |
   |                       |                                                                                        |                       |
   |                       |                                                                                        | **Constraints**       |
   |                       |                                                                                        |                       |
   |                       |                                                                                        | N/A                   |
   |                       |                                                                                        |                       |
   |                       |                                                                                        | **Range**             |
   |                       |                                                                                        |                       |
   |                       |                                                                                        | N/A                   |
   |                       |                                                                                        |                       |
   |                       |                                                                                        | **Default Value**     |
   |                       |                                                                                        |                       |
   |                       |                                                                                        | N/A                   |
   +-----------------------+----------------------------------------------------------------------------------------+-----------------------+

.. _showquotas__response_quotaresourceentity:

.. table:: **Table 5** QuotaResourceEntity

   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                    |
   +=======================+=======================+================================================================================================================================+
   | type                  | String                | **Definition**                                                                                                                 |
   |                       |                       |                                                                                                                                |
   |                       |                       | Supports kafkaInstance, rocketmqInstance, and tags.                                                                            |
   |                       |                       |                                                                                                                                |
   |                       |                       | -  **kafkaInstance**: Kafka instance quotas                                                                                    |
   |                       |                       |                                                                                                                                |
   |                       |                       | -  **rocketmqInstance**: RocketMQ instance quotas                                                                              |
   |                       |                       |                                                                                                                                |
   |                       |                       | -  **tags**: Tag quotas                                                                                                        |
   |                       |                       |                                                                                                                                |
   |                       |                       | -  **kafkaInstancePublic**: Kafka public network quotas (deprecated).                                                          |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Constraints**                                                                                                                |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Range**                                                                                                                      |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Default Value**                                                                                                              |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | quota                 | Integer               | **Definition**                                                                                                                 |
   |                       |                       |                                                                                                                                |
   |                       |                       | The maximum number of instances that a tenant can create, or the maximum number of tags that can be created for each instance. |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Constraints**                                                                                                                |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Range**                                                                                                                      |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Default Value**                                                                                                              |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------+
   | used                  | Integer               | **Definition**                                                                                                                 |
   |                       |                       |                                                                                                                                |
   |                       |                       | Number of created instances.                                                                                                   |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Constraints**                                                                                                                |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Range**                                                                                                                      |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   |                       |                       |                                                                                                                                |
   |                       |                       | **Default Value**                                                                                                              |
   |                       |                       |                                                                                                                                |
   |                       |                       | N/A                                                                                                                            |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/quotas?includeTagsQuota=false&onlyQuota=reliability

Example Responses
-----------------

**Status code: 200**

Successful

.. code-block::

   {
     "quotas" : {
       "resources" : [ {
         "type" : "rocketmqInstance",
         "quota" : 100,
         "used" : 17
       } ]
     }
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         Successful
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
