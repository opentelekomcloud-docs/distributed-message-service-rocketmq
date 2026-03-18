:original_name: ShowRocketmqProjectTags.html

.. _ShowRocketmqProjectTags:

Querying Project Tags
=====================

Function
--------

This API is used to query tags of a project.

URI
---

GET /v2/{project_id}/rocketmq/tags

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

   +-----------------+-----------------+-----------------+--------------------------------+
   | Parameter       | Mandatory       | Type            | Description                    |
   +=================+=================+=================+================================+
   | limit           | No              | Integer         | **Definition**                 |
   |                 |                 |                 |                                |
   |                 |                 |                 | Number of records to query.    |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Constraints**                |
   |                 |                 |                 |                                |
   |                 |                 |                 | N/A                            |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Range**                      |
   |                 |                 |                 |                                |
   |                 |                 |                 | N/A                            |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Default value**              |
   |                 |                 |                 |                                |
   |                 |                 |                 | 10                             |
   +-----------------+-----------------+-----------------+--------------------------------+
   | offset          | No              | Integer         | **Definition**                 |
   |                 |                 |                 |                                |
   |                 |                 |                 | Offset where the query starts. |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Constraints**                |
   |                 |                 |                 |                                |
   |                 |                 |                 | N/A                            |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Range**                      |
   |                 |                 |                 |                                |
   |                 |                 |                 | >= 0                           |
   |                 |                 |                 |                                |
   |                 |                 |                 | **Default Value**              |
   |                 |                 |                 |                                |
   |                 |                 |                 | 0                              |
   +-----------------+-----------------+-----------------+--------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+-----------------------------------------------------------------------------------------------------+------------------------------+
   | Parameter             | Type                                                                                                | Description                  |
   +=======================+=====================================================================================================+==============================+
   | total                 | Number                                                                                              | **Definition**               |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | Total number.                |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Constraints**              |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Range**                    |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Default Value**            |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------------------------------+------------------------------+
   | next_offset           | Integer                                                                                             | **Definition**               |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | Offset of the next page.     |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Constraints**              |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Range**                    |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Default Value**            |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------------------------------+------------------------------+
   | previous_offset       | Integer                                                                                             | **Definition**               |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | Offset of the previous page. |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Constraints**              |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Range**                    |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Default Value**            |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------------------------------+------------------------------+
   | tags                  | Array of :ref:`TagMultyValueEntity <showrocketmqprojecttags__response_tagmultyvalueentity>` objects | **Definition**               |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | Tag list.                    |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Constraints**              |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Range**                    |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | **Default Value**            |
   |                       |                                                                                                     |                              |
   |                       |                                                                                                     | N/A                          |
   +-----------------------+-----------------------------------------------------------------------------------------------------+------------------------------+

.. _showrocketmqprojecttags__response_tagmultyvalueentity:

.. table:: **Table 4** TagMultyValueEntity

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | key                   | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Tag key.              |
   |                       |                       |                       |
   |                       |                       | **Constraints**       |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   |                       |                       |                       |
   |                       |                       | **Range**             |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   |                       |                       |                       |
   |                       |                       | **Default Value**     |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   +-----------------------+-----------------------+-----------------------+
   | values                | Array of strings      | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Tag value.            |
   |                       |                       |                       |
   |                       |                       | **Constraints**       |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   |                       |                       |                       |
   |                       |                       | **Range**             |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   |                       |                       |                       |
   |                       |                       | **Default Value**     |
   |                       |                       |                       |
   |                       |                       | N/A                   |
   +-----------------------+-----------------------+-----------------------+

Example Requests
----------------

Querying project tags

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/rocketmq/tags

Example Responses
-----------------

**Status code: 200**

The project tags are queried successfully.

.. code-block::

   {
     "total" : 1,
     "next_offset" : -1,
     "previous_offset" : -1,
     "tags" : [ {
       "key" : "key1",
       "values" : [ "value-test", "value1" ]
     }, {
       "key" : "key2",
       "values" : [ "value2" ]
     } ]
   }

Status Codes
------------

=========== ==========================================
Status Code Description
=========== ==========================================
200         The project tags are queried successfully.
=========== ==========================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
