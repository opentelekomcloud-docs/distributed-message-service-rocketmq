:original_name: ListInstanceConsumerGroups.html

.. _ListInstanceConsumerGroups:

Querying the Consumer Group List
================================

Function
--------

This API is used to query the consumer group list.

URI
---

GET /v2/{project_id}/instances/{instance_id}/groups

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

   +-----------------+-----------------+-----------------+--------------------------------+
   | Parameter       | Mandatory       | Type            | Description                    |
   +=================+=================+=================+================================+
   | group           | No              | String          | **Definition**                 |
   |                 |                 |                 |                                |
   |                 |                 |                 | Consumer group name.           |
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
   |                 |                 |                 | N/A                            |
   +-----------------+-----------------+-----------------+--------------------------------+
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
   |                 |                 |                 | **Default value**              |
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

   +-----------------------+--------------------------------------------------------------------------------------------+----------------------------------------------------------+
   | Parameter             | Type                                                                                       | Description                                              |
   +=======================+============================================================================================+==========================================================+
   | total                 | Number                                                                                     | **Definition**                                           |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | Total number of consumer groups.                         |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Constraints**                                          |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Range**                                                |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Default Value**                                        |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   +-----------------------+--------------------------------------------------------------------------------------------+----------------------------------------------------------+
   | groups                | Array of :ref:`ConsumerGroup <listinstanceconsumergroups__response_consumergroup>` objects | **Definition**                                           |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | Consumer group list.                                     |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Constraints**                                          |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Range**                                                |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Default Value**                                        |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   +-----------------------+--------------------------------------------------------------------------------------------+----------------------------------------------------------+
   | max                   | Integer                                                                                    | **Definition**                                           |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | Maximum number of consumer groups that can be created.   |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Constraints**                                          |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Range**                                                |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Default Value**                                        |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   +-----------------------+--------------------------------------------------------------------------------------------+----------------------------------------------------------+
   | remaining             | Integer                                                                                    | **Definition**                                           |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | Remaining number of consumer groups that can be created. |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Constraints**                                          |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Range**                                                |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Default Value**                                        |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   +-----------------------+--------------------------------------------------------------------------------------------+----------------------------------------------------------+
   | next_offset           | Integer                                                                                    | **Definition**                                           |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | Offset of the next page.                                 |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Constraints**                                          |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Range**                                                |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Default Value**                                        |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   +-----------------------+--------------------------------------------------------------------------------------------+----------------------------------------------------------+
   | previous_offset       | Integer                                                                                    | **Definition**                                           |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | Offset of the previous page.                             |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Constraints**                                          |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Range**                                                |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | **Default Value**                                        |
   |                       |                                                                                            |                                                          |
   |                       |                                                                                            | N/A                                                      |
   +-----------------------+--------------------------------------------------------------------------------------------+----------------------------------------------------------+

.. _listinstanceconsumergroups__response_consumergroup:

.. table:: **Table 4** ConsumerGroup

   +-----------------------+-----------------------+-----------------------------------------+
   | Parameter             | Type                  | Description                             |
   +=======================+=======================+=========================================+
   | enabled               | Boolean               | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Whether consumption is allowed.         |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | -  **true**: Yes                        |
   |                       |                       |                                         |
   |                       |                       | -  **false**: No                        |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | broadcast             | Boolean               | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Whether to enable broadcast.            |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | -  **true**: Yes                        |
   |                       |                       |                                         |
   |                       |                       | -  **false**: No                        |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | brokers               | Array of strings      | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | List of associated brokers.             |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | name                  | String                | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Consumer group name.                    |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | group_desc            | String                | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Consumer group description.             |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | retry_max_time        | Integer               | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Maximum number of retries.              |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | 1-16                                    |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | created_at            | Long                  | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Creation time.                          |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | permissions           | Array of strings      | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Permission set.                         |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | consume_orderly       | Boolean               | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Whether orderly consumption is enabled. |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | -  **true**: Yes                        |
   |                       |                       |                                         |
   |                       |                       | -  **false**: No                        |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+
   | group_online          | Boolean               | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Whether the consumer group is online.   |
   |                       |                       |                                         |
   |                       |                       | **Constraints**                         |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   |                       |                       |                                         |
   |                       |                       | **Range**                               |
   |                       |                       |                                         |
   |                       |                       | -  **true**: Yes                        |
   |                       |                       |                                         |
   |                       |                       | -  **false**: No                        |
   |                       |                       |                                         |
   |                       |                       | **Default Value**                       |
   |                       |                       |                                         |
   |                       |                       | N/A                                     |
   +-----------------------+-----------------------+-----------------------------------------+

Example Requests
----------------

Querying the consumer group list of a RocketMQ instance

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/groups

Example Responses
-----------------

**Status code: 200**

Consumer groups queried successfully.

.. code-block::

   {
     "total" : 1,
     "groups" : [ {
       "name" : "group-1",
       "enabled" : true,
       "broadcast" : false,
       "brokers" : [ "broker-0" ],
       "permissions" : [ ],
       "retry_max_time" : 16,
       "consume_orderly" : false,
       "group_online" : false,
       "group_desc" : "test",
       "created_at" : 1709087952686
     } ],
     "max" : 4000,
     "remaining" : 3999,
     "next_offset" : -1,
     "previous_offset" : -1
   }

Status Codes
------------

=========== =====================================
Status Code Description
=========== =====================================
200         Consumer groups queried successfully.
=========== =====================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
