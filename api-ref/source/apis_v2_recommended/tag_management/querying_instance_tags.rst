:original_name: ShowRocketmqTags.html

.. _ShowRocketmqTags:

Querying Instance Tags
======================

Function
--------

This API is used to query instance tags.

URI
---

GET /v2/{project_id}/rocketmq/{instance_id}/tags

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

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                         |
   +=================+=================+=================+=====================================================================================================+
   | limit           | No              | Integer         | **Definition**                                                                                      |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | Number of records to query.                                                                         |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                     |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Range**                                                                                           |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                   |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | 10                                                                                                  |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------+
   | offset          | No              | Integer         | **Definition**                                                                                      |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | Offset, which is the position where the query starts. The value must be greater than or equal to 0. |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Constraints**                                                                                     |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Range**                                                                                           |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | N/A                                                                                                 |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | **Default Value**                                                                                   |
   |                 |                 |                 |                                                                                                     |
   |                 |                 |                 | 0                                                                                                   |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+--------------------------------------------------------------------------+------------------------------+
   | Parameter             | Type                                                                     | Description                  |
   +=======================+==========================================================================+==============================+
   | total                 | Number                                                                   | **Definition**               |
   |                       |                                                                          |                              |
   |                       |                                                                          | Total number.                |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Constraints**              |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Range**                    |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Default Value**            |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   +-----------------------+--------------------------------------------------------------------------+------------------------------+
   | next_offset           | Integer                                                                  | **Definition**               |
   |                       |                                                                          |                              |
   |                       |                                                                          | Offset of the next page.     |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Constraints**              |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Range**                    |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Default Value**            |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   +-----------------------+--------------------------------------------------------------------------+------------------------------+
   | previous_offset       | Integer                                                                  | **Definition**               |
   |                       |                                                                          |                              |
   |                       |                                                                          | Offset of the previous page. |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Constraints**              |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Range**                    |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Default Value**            |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   +-----------------------+--------------------------------------------------------------------------+------------------------------+
   | tags                  | Array of :ref:`TagEntity <showrocketmqtags__response_tagentity>` objects | **Definition**               |
   |                       |                                                                          |                              |
   |                       |                                                                          | Tag list.                    |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Constraints**              |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Range**                    |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   |                       |                                                                          |                              |
   |                       |                                                                          | **Default Value**            |
   |                       |                                                                          |                              |
   |                       |                                                                          | N/A                          |
   +-----------------------+--------------------------------------------------------------------------+------------------------------+

.. _showrocketmqtags__response_tagentity:

.. table:: **Table 4** TagEntity

   +-----------------------+-----------------------+-------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                             |
   +=======================+=======================+=========================================================================+
   | key                   | String                | Tag key.                                                                |
   |                       |                       |                                                                         |
   |                       |                       | -  Must be specified.                                                   |
   |                       |                       |                                                                         |
   |                       |                       | -  Must be unique for the same instance.                                |
   |                       |                       |                                                                         |
   |                       |                       | -  Can contain 1 to 128 characters.                                     |
   |                       |                       |                                                                         |
   |                       |                       | -  Can contain letters, digits, spaces, and special characters \_.:=+-@ |
   |                       |                       |                                                                         |
   |                       |                       | -  Cannot start or end with a space.                                    |
   +-----------------------+-----------------------+-------------------------------------------------------------------------+
   | value                 | String                | Tag value.                                                              |
   |                       |                       |                                                                         |
   |                       |                       | -  Can contain 0 to 255 characters.                                     |
   |                       |                       |                                                                         |
   |                       |                       | -  Can contain letters, digits, spaces, and special characters \_.:=+-@ |
   |                       |                       |                                                                         |
   |                       |                       | -  Cannot start or end with a space.                                    |
   +-----------------------+-----------------------+-------------------------------------------------------------------------+

Example Requests
----------------

Querying instance tags

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/rocketmq/{instance_id}/tags

Example Responses
-----------------

**Status code: 200**

Instance tags queried successfully.

.. code-block::

   {
     "total" : 1,
     "next_offset" : -1,
     "previous_offset" : -1,
     "tags" : [ {
       "key" : "key1",
       "value" : "value1"
     }, {
       "key" : "key2",
       "value" : "value2"
     } ]
   }

Status Codes
------------

=========== ===================================
Status Code Description
=========== ===================================
200         Instance tags queried successfully.
=========== ===================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
