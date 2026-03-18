:original_name: ShowCesHierarchy.html

.. _ShowCesHierarchy:

Querying Instance Monitoring Dimensions
=======================================

Function
--------

This API is used to query instance monitoring dimensions.

URI
---

GET /v2/{project_id}/instances/{instance_id}/ces-hierarchy

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

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------------------+--------------------------------------------------------------------------------+-----------------------------+
   | Parameter             | Type                                                                           | Description                 |
   +=======================+================================================================================+=============================+
   | dimensions            | Array of :ref:`dimensions <showceshierarchy__response_dimensions>` objects     | **Definition**              |
   |                       |                                                                                |                             |
   |                       |                                                                                | Monitoring dimensions.      |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Constraints**             |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Range**                   |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Default Value**           |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   +-----------------------+--------------------------------------------------------------------------------+-----------------------------+
   | instance_ids          | Array of :ref:`instance_ids <showceshierarchy__response_instance_ids>` objects | **Definition**              |
   |                       |                                                                                |                             |
   |                       |                                                                                | Instance information.       |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Constraints**             |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Range**                   |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Default Value**           |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   +-----------------------+--------------------------------------------------------------------------------+-----------------------------+
   | nodes                 | Array of :ref:`nodes <showceshierarchy__response_nodes>` objects               | **Definition**              |
   |                       |                                                                                |                             |
   |                       |                                                                                | Node information.           |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Constraints**             |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Range**                   |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Default Value**           |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   +-----------------------+--------------------------------------------------------------------------------+-----------------------------+
   | topics                | Array of :ref:`topics <showceshierarchy__response_topics>` objects             | **Definition**              |
   |                       |                                                                                |                             |
   |                       |                                                                                | Queue information.          |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Constraints**             |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Range**                   |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Default Value**           |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   +-----------------------+--------------------------------------------------------------------------------+-----------------------------+
   | dlq                   | Array of :ref:`dlq <showceshierarchy__response_dlq>` objects                   | **Definition**              |
   |                       |                                                                                |                             |
   |                       |                                                                                | Dead letter queue.          |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Constraints**             |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Range**                   |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Default Value**           |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   +-----------------------+--------------------------------------------------------------------------------+-----------------------------+
   | groups                | Array of :ref:`groups <showceshierarchy__response_groups>` objects             | **Definition**              |
   |                       |                                                                                |                             |
   |                       |                                                                                | Consumer group information. |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Constraints**             |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Range**                   |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   |                       |                                                                                |                             |
   |                       |                                                                                | **Default Value**           |
   |                       |                                                                                |                             |
   |                       |                                                                                | N/A                         |
   +-----------------------+--------------------------------------------------------------------------------+-----------------------------+

.. _showceshierarchy__response_dimensions:

.. table:: **Table 3** dimensions

   +-----------------------+------------------------------------------------------------------------+--------------------------------+
   | Parameter             | Type                                                                   | Description                    |
   +=======================+========================================================================+================================+
   | name                  | String                                                                 | **Definition**                 |
   |                       |                                                                        |                                |
   |                       |                                                                        | Monitoring dimension name.     |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Constraints**                |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Range**                      |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Default Value**              |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   +-----------------------+------------------------------------------------------------------------+--------------------------------+
   | metrics               | Array of strings                                                       | **Definition**                 |
   |                       |                                                                        |                                |
   |                       |                                                                        | Metric name.                   |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Constraints**                |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Range**                      |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Default Value**              |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   +-----------------------+------------------------------------------------------------------------+--------------------------------+
   | key_name              | Array of strings                                                       | **Definition**                 |
   |                       |                                                                        |                                |
   |                       |                                                                        | Key used for monitoring query. |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Constraints**                |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Range**                      |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Default Value**              |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   +-----------------------+------------------------------------------------------------------------+--------------------------------+
   | dim_router            | Array of strings                                                       | **Definition**                 |
   |                       |                                                                        |                                |
   |                       |                                                                        | Monitoring dimension route.    |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Constraints**                |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Range**                      |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Default Value**              |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   +-----------------------+------------------------------------------------------------------------+--------------------------------+
   | children              | Array of :ref:`children <showceshierarchy__response_children>` objects | **Definition**                 |
   |                       |                                                                        |                                |
   |                       |                                                                        | List of secondary dimensions.  |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Constraints**                |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Range**                      |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   |                       |                                                                        |                                |
   |                       |                                                                        | **Default Value**              |
   |                       |                                                                        |                                |
   |                       |                                                                        | N/A                            |
   +-----------------------+------------------------------------------------------------------------+--------------------------------+

.. _showceshierarchy__response_children:

.. table:: **Table 4** children

   +-----------------------+-----------------------+----------------------------------+
   | Parameter             | Type                  | Description                      |
   +=======================+=======================+==================================+
   | name                  | String                | **Definition**                   |
   |                       |                       |                                  |
   |                       |                       | Secondary dimension name.        |
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
   | metrics               | Array of strings      | **Definition**                   |
   |                       |                       |                                  |
   |                       |                       | List of monitoring metric names. |
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
   | key_name              | Array of strings      | **Definition**                   |
   |                       |                       |                                  |
   |                       |                       | Key used for monitoring query.   |
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
   | dim_router            | Array of strings      | **Definition**                   |
   |                       |                       |                                  |
   |                       |                       | Monitoring dimension route.      |
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

.. _showceshierarchy__response_instance_ids:

.. table:: **Table 5** instance_ids

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | name                  | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Instance ID.          |
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

.. _showceshierarchy__response_nodes:

.. table:: **Table 6** nodes

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | name                  | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Node name.            |
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

.. _showceshierarchy__response_topics:

.. table:: **Table 7** topics

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | name                  | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Topic name.           |
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

.. _showceshierarchy__response_dlq:

.. table:: **Table 8** dlq

   +-----------------------+-----------------------+-------------------------+
   | Parameter             | Type                  | Description             |
   +=======================+=======================+=========================+
   | name                  | String                | **Definition**          |
   |                       |                       |                         |
   |                       |                       | Dead letter queue name. |
   |                       |                       |                         |
   |                       |                       | **Constraints**         |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   |                       |                       |                         |
   |                       |                       | **Range**               |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   |                       |                       |                         |
   |                       |                       | **Default Value**       |
   |                       |                       |                         |
   |                       |                       | N/A                     |
   +-----------------------+-----------------------+-------------------------+

.. _showceshierarchy__response_groups:

.. table:: **Table 9** groups

   +-----------------------+----------------------------------------------------------------------+---------------------------------+
   | Parameter             | Type                                                                 | Description                     |
   +=======================+======================================================================+=================================+
   | name                  | String                                                               | **Definition**                  |
   |                       |                                                                      |                                 |
   |                       |                                                                      | Consumer group name.            |
   |                       |                                                                      |                                 |
   |                       |                                                                      | **Constraints**                 |
   |                       |                                                                      |                                 |
   |                       |                                                                      | N/A                             |
   |                       |                                                                      |                                 |
   |                       |                                                                      | **Range**                       |
   |                       |                                                                      |                                 |
   |                       |                                                                      | N/A                             |
   |                       |                                                                      |                                 |
   |                       |                                                                      | **Default Value**               |
   |                       |                                                                      |                                 |
   |                       |                                                                      | N/A                             |
   +-----------------------+----------------------------------------------------------------------+---------------------------------+
   | topics                | Array of :ref:`topics <showceshierarchy__response_topics_1>` objects | **Definition**                  |
   |                       |                                                                      |                                 |
   |                       |                                                                      | Topic subscription information. |
   |                       |                                                                      |                                 |
   |                       |                                                                      | **Constraints**                 |
   |                       |                                                                      |                                 |
   |                       |                                                                      | N/A                             |
   |                       |                                                                      |                                 |
   |                       |                                                                      | **Range**                       |
   |                       |                                                                      |                                 |
   |                       |                                                                      | N/A                             |
   |                       |                                                                      |                                 |
   |                       |                                                                      | **Default Value**               |
   |                       |                                                                      |                                 |
   |                       |                                                                      | N/A                             |
   +-----------------------+----------------------------------------------------------------------+---------------------------------+

.. _showceshierarchy__response_topics_1:

.. table:: **Table 10** topics

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | name                  | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Topic name.           |
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

.. code-block:: text

   GET https://{endpoint}/v2/{project_id}/instances/{instance_id}/ces-hierarchy

Example Responses
-----------------

**Status code: 200**

Queried.

.. code-block::

   {
     "dimensions" : [ {
       "name" : "reliablemq_instance_id",
       "metrics" : [ "instance_produce_msg", "instance_consume_msg" ],
       "key_name" : [ "instance_ids" ],
       "dim_router" : [ "reliablemq_instance_id" ]
     }, {
       "name" : "reliablemq_broker",
       "metrics" : [ "broker_produce_msg", "broker_consume_msg", "broker_produce_rate", "broker_consume_rate", "broker_total_bytes_in_rate", "broker_total_bytes_out_rate", "broker_cpu_core_load", "broker_disk_usage", "broker_memory_usage" ],
       "key_name" : [ "nodes" ],
       "dim_router" : [ "reliablemq_instance_id", "reliablemq_broker" ]
     }, {
       "name" : "reliablemq_topics",
       "metrics" : [ "topic_produce_msg", "topic_consume_msg", "topic_produce_rate", "topic_consume_rate" ],
       "key_name" : [ "topics" ],
       "dim_router" : [ "reliablemq_instance_id", "reliablemq_topics" ]
     }, {
       "name" : "reliablemq_groups",
       "metrics" : [ "group_consume_msg", "group_accumulation" ],
       "key_name" : [ "groups" ],
       "dim_router" : [ "reliablemq_instance_id", "reliablemq_groups" ],
       "children" : [ {
         "name" : "reliablemq_groups_topics",
         "metrics" : [ "group_topic_consume_msg", "group_topic_consume_rate", "group_topic_accumulation" ],
         "key_name" : [ "groups", "topics" ],
         "dim_router" : [ "reliablemq_instance_id", "reliablemq_groups", "reliablemq_groups_topics" ]
       } ]
     }, {
       "name" : "reliablemq_dlq_topics",
       "metrics" : [ "dlq_accumulation" ],
       "key_name" : [ "dlq" ],
       "dim_router" : [ "reliablemq_instance_id", "reliablemq_dlq_topics" ]
     } ],
     "instance_ids" : [ {
       "name" : "af82f7a9-5636-4898-85e4-200fe0fab361"
     } ],
     "nodes" : [ ],
     "topics" : [ {
       "name" : "dingshi"
     }, {
       "name" : "lala"
     }, {
       "name" : "shunxu"
     } ],
     "dlq" : [ {
       "name" : "DLQ_group-1"
     }, {
       "name" : "DLQ_group-1000"
     }, {
       "name" : "DLQ_group-2"
     }, {
       "name" : "DLQ_group-3"
     }, {
       "name" : "DLQ_group-4"
     }, {
       "name" : "DLQ_group-5"
     }, {
       "name" : "DLQ_group-6"
     }, {
       "name" : "DLQ_group-7"
     }, {
       "name" : "DLQ_group-8"
     }, {
       "name" : "DLQ_group-9"
     }, {
       "name" : "DLQ_group-dingshi"
     }, {
       "name" : "DLQ_group-shunxu"
     }, {
       "name" : "DLQ_group101010"
     } ],
     "groups" : [ {
       "name" : "group-shunxu",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-7",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-dingshi",
       "topics" : [ {
         "name" : "dingshi"
       } ]
     }, {
       "name" : "group-6",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-9",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-8",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-3",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-2",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-5",
       "topics" : [ {
         "name" : "dingshi"
       }, {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-4",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group101010",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-1000",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     }, {
       "name" : "group-1",
       "topics" : [ {
         "name" : "shunxu"
       } ]
     } ]
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         Queried.
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
