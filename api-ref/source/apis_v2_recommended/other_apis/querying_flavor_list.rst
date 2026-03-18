:original_name: ListEngineProducts.html

.. _ListEngineProducts:

Querying Flavor List
====================

Function
--------

This API is used to query the flavor list of an engine.

URI
---

GET /v2/{engine}/products

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+----------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                        |
   +=================+=================+=================+====================================================+
   | engine          | Yes             | String          | **Definition**                                     |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | Message engine type.                               |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | **Constraints**                                    |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | N/A                                                |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | **Range**                                          |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | -  **rocketmq**: RocketMQ message engine.          |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | -  **reliability**: RocketMQ message engine alias. |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | **Default Value**                                  |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | rocketmq                                           |
   +-----------------+-----------------+-----------------+----------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                            |
   +=================+=================+=================+========================================================================================================================+
   | product_id      | No              | String          | **Definition**                                                                                                         |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | RocketMQ instance flavors.                                                                                             |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Constraints**                                                                                                        |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | N/A                                                                                                                    |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Range**                                                                                                              |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | If **type** is **single.basic**, select single-node flavors. If **type** is **cluster.basic**, select cluster flavors. |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | -  **rocketmq.b1.large.1**: RocketMQ 5.x basic edition single-node flavor, instance TPS 500                            |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | -  **rocketmq.b2.large.4**: RocketMQ 5.x basic edition cluster flavor, instance TPS 2,000                              |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | -  **rocketmq.b2.large.8**: RocketMQ 5.x basic edition cluster flavor, instance TPS 4,000                              |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | -  **rocketmq.b2.large.12**: RocketMQ 5.x basic edition cluster flavor, instance TPS 6,000                             |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Default Value**                                                                                                      |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | N/A                                                                                                                    |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | Integer         | **Definition**                                                                                                         |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | Number of records to query.                                                                                            |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Constraints**                                                                                                        |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | N/A                                                                                                                    |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Range**                                                                                                              |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | N/A                                                                                                                    |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Default value**                                                                                                      |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | 10                                                                                                                     |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | Integer         | **Definition**                                                                                                         |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | Offset where the query starts.                                                                                         |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Constraints**                                                                                                        |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | N/A                                                                                                                    |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Range**                                                                                                              |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | >= 0                                                                                                                   |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | **Default Value**                                                                                                      |
   |                 |                 |                 |                                                                                                                        |
   |                 |                 |                 | 0                                                                                                                      |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+------------------------------------------------------------------------------------+----------------------------------------------------+
   | Parameter             | Type                                                                               | Description                                        |
   +=======================+====================================================================================+====================================================+
   | total                 | Number                                                                             | **Definition**                                     |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | Total number.                                      |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Constraints**                                    |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Range**                                          |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | >= 0                                               |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Default Value**                                  |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   +-----------------------+------------------------------------------------------------------------------------+----------------------------------------------------+
   | next_offset           | Integer                                                                            | **Definition**                                     |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | Offset of the next page.                           |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Constraints**                                    |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Range**                                          |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Default Value**                                  |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   +-----------------------+------------------------------------------------------------------------------------+----------------------------------------------------+
   | previous_offset       | Integer                                                                            | **Definition**                                     |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | Offset of the previous page.                       |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Constraints**                                    |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Range**                                          |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Default Value**                                  |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   +-----------------------+------------------------------------------------------------------------------------+----------------------------------------------------+
   | engine                | String                                                                             | **Definition**                                     |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | Engine type.                                       |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Constraints**                                    |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Range**                                          |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | -  **rocketmq**: RocketMQ message engine.          |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | -  **reliability**: RocketMQ message engine alias. |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Default Value**                                  |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   +-----------------------+------------------------------------------------------------------------------------+----------------------------------------------------+
   | versions              | Array of strings                                                                   | **Definition**                                     |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | Supported versions.                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Constraints**                                    |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Range**                                          |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Default Value**                                  |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   +-----------------------+------------------------------------------------------------------------------------+----------------------------------------------------+
   | products              | Array of :ref:`ProductEntity <listengineproducts__response_productentity>` objects | **Definition**                                     |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | Instance details.                                  |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Constraints**                                    |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Range**                                          |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | **Default Value**                                  |
   |                       |                                                                                    |                                                    |
   |                       |                                                                                    | N/A                                                |
   +-----------------------+------------------------------------------------------------------------------------+----------------------------------------------------+

.. _listengineproducts__response_productentity:

.. table:: **Table 4** ProductEntity

   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                       | Description                                                                                                                                                                    |
   +=======================+============================================================================+================================================================================================================================================================================+
   | type                  | String                                                                     | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | Product type.                                                                                                                                                                  |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **single.basic**: 5.x single-node basic edition.                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **cluster.basic**: 5.x cluster basic edition                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | product_id            | String                                                                     | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | RocketMQ instance flavors. This API is shared with other engines, so product flavors of other RocketMQ versions may be returned.                                               |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | If **type** is **single.basic**, select single-node flavors. If **type** is **cluster.basic**, select cluster flavors.                                                         |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **rocketmq.b1.large.1**: RocketMQ 5.x basic edition single-node flavor, instance TPS 500                                                                                    |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **rocketmq.b2.large.4**: RocketMQ 5.x basic edition cluster flavor, instance TPS 2,000                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **rocketmq.b2.large.8**: RocketMQ 5.x basic edition cluster flavor, instance TPS 4,000                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **rocketmq.b2.large.12**: RocketMQ 5.x basic edition cluster flavor, instance TPS 6,000                                                                                     |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ecs_flavor_id         | String                                                                     | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | ID of an ECS flavor. The specifications list of ECS can be referred. DMS can be adapted with general computing-plus C6 series and later. RocketMQ 5.x CPU/memory ratio is 1:4. |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | billing_code          | String                                                                     | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | CBC flavor code.                                                                                                                                                               |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **dms.rocketmq.basic.single.tps**: single-node RocketMQ 5.x basic edition.                                                                                                  |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **dms.rocketmq.basic.cluster.tps**: cluster RocketMQ 5.x basic edition.                                                                                                     |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | arch_types            | Array of strings                                                           | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | Supported architectures.                                                                                                                                                       |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | charging_mode         | Array of strings                                                           | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | Billing mode.                                                                                                                                                                  |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ios                   | Array of :ref:`IOSEntity <listengineproducts__response_iosentity>` objects | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | Supported I/O types.                                                                                                                                                           |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | support_features      | Array of strings                                                           | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | Supported feature list.                                                                                                                                                        |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | properties            | :ref:`properties <listengineproducts__response_properties>` object         | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | Product features.                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | qingtian_incompatible | Boolean                                                                    | **Definition**                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | Whether the instance is a QingTian one.                                                                                                                                        |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Constraints**                                                                                                                                                                |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Range**                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **true**: Yes                                                                                                                                                               |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | -  **false**: No                                                                                                                                                               |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | **Default Value**                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                |
   |                       |                                                                            | N/A                                                                                                                                                                            |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _listengineproducts__response_iosentity:

.. table:: **Table 5** IOSEntity

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                             |
   +=======================+=======================+=========================================================================================================================+
   | available_zones       | Array of strings      | **Definition**                                                                                                          |
   |                       |                       |                                                                                                                         |
   |                       |                       | AZ list. For RocketMQ 5.x basic edition: Select one AZ for a single-node instance and one or two AZs for a cluster one. |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Constraints**                                                                                                         |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Range**                                                                                                               |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Default Value**                                                                                                       |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------+
   | unavailable_zones     | Array of strings      | **Definition**                                                                                                          |
   |                       |                       |                                                                                                                         |
   |                       |                       | Unavailable AZ list.                                                                                                    |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Constraints**                                                                                                         |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Range**                                                                                                               |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Default Value**                                                                                                       |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------+
   | io_spec               | String                | **Definition**                                                                                                          |
   |                       |                       |                                                                                                                         |
   |                       |                       | Storage flavor code.                                                                                                    |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Constraints**                                                                                                         |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Range**                                                                                                               |
   |                       |                       |                                                                                                                         |
   |                       |                       | -  **dms.physical.storage.high.v2**: high I/O disk                                                                      |
   |                       |                       |                                                                                                                         |
   |                       |                       | -  **dms.physical.storage.ultra.v2**: ultra-high I/O disk                                                               |
   |                       |                       |                                                                                                                         |
   |                       |                       | -  **dms.physical.storage.general**: general-purpose SSD                                                                |
   |                       |                       |                                                                                                                         |
   |                       |                       | -  **dms.physical.storage.extreme**: extreme SSD                                                                        |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Default Value**                                                                                                       |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------+
   | type                  | String                | **Definition**                                                                                                          |
   |                       |                       |                                                                                                                         |
   |                       |                       | Service type to which storage belongs.                                                                                  |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Constraints**                                                                                                         |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Range**                                                                                                               |
   |                       |                       |                                                                                                                         |
   |                       |                       | evs                                                                                                                     |
   |                       |                       |                                                                                                                         |
   |                       |                       | **Default Value**                                                                                                       |
   |                       |                       |                                                                                                                         |
   |                       |                       | N/A                                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------+

.. _listengineproducts__response_properties:

.. table:: **Table 6** properties

   +-------------------------+-----------------------+--------------------------------------------------------------+
   | Parameter               | Type                  | Description                                                  |
   +=========================+=======================+==============================================================+
   | max_topic               | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Maximum number of topics.                                    |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | broker_num              | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Broker quantity.                                             |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | core                    | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Number of billing cores of an entire instance.               |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | max_consumer            | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Maximum number of consumers in an instance.                  |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | rcu                     | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Traffic unit, rcu x max_tpc_per_rcu = Maximum flavor TPS.    |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | max_storage             | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Maximum storage space, in GB.                                |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | max_storage_per_node    | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Maximum storage space of each node, in GB.                   |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | product_alias           | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Alias of **product_id**.                                     |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | max_tps_per_rcu         | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Maximum TPS of each RCU.                                     |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | engine_versions         | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Message engine version.                                      |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | -  **5.x**                                                   |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | min_storage             | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Minimum storage space, in GB.                                |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | min_storage_per_node    | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Minimum storage per node. Unit: GB.                          |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | max_broker              | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Maximum number of brokers.                                   |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | max_topic_per_broker    | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Maximum number of topics that can be created on each broker. |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | max_consumer_per_broker | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Maximum number of consumers on each broker.                  |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+
   | min_broker              | String                | **Definition**                                               |
   |                         |                       |                                                              |
   |                         |                       | Minimum number of brokers.                                   |
   |                         |                       |                                                              |
   |                         |                       | **Constraints**                                              |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Range**                                                    |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   |                         |                       |                                                              |
   |                         |                       | **Default Value**                                            |
   |                         |                       |                                                              |
   |                         |                       | N/A                                                          |
   +-------------------------+-----------------------+--------------------------------------------------------------+

Example Requests
----------------

.. code-block:: text

   GET https://{endpoint}/v2/reliability/products?product_id=rocketmq.b1.large.1

Example Responses
-----------------

**Status code: 200**

Successful

.. code-block::

   {
     "total" : 1,
     "next_offset" : -1,
     "previous_offset" : -1,
     "engine" : "rocketmq",
     "versions" : [ "5.x" ],
     "products" : [ {
       "type" : "single.basic",
       "product_id" : "rocketmq.b1.large.1",
       "ecs_flavor_id" : "c6.large.2",
       "billing_code" : "dms.rocketmq.basic.single.tps",
       "arch_types" : [ "X86" ],
       "charging_mode" : [ "monthly", "hourly" ],
       "ios" : [ {
         "io_spec" : "dms.physical.storage.high.v2",
         "available_zones" : [ "cn-southwest-xxa", "cn-southwest-xxb" ],
         "type" : "evs",
         "unavailable_zones" : [ "cn-southwest-xxc" ]
       }, {
         "io_spec" : "dms.physical.storage.ultra.v2",
         "available_zones" : [ "cn-southwest-xxa", "cn-southwest-xxb" ],
         "type" : "evs",
         "unavailable_zones" : [ "cn-southwest-xxc" ]
       } ],
       "support_features" : [ ],
       "properties" : {
         "max_topic" : 50,
         "broker_num" : 1,
         "core" : 1,
         "max_consumer" : 500,
         "rcu" : 1,
         "max_storage" : 30000,
         "max_storage_per_node" : 90000,
         "min_storage" : 100,
         "product_alias" : "rocketmq.b1.large.1",
         "max_tps_per_rcu" : 500,
         "engine_versions" : "5.x",
         "min_storage_per_node" : 300
       },
       "qingtian_incompatible" : false
     } ]
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
