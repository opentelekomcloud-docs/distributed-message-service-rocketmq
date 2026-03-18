:original_name: ListAvailableZones.html

.. _ListAvailableZones:

Querying AZ Information
=======================

Function
--------

This API is used to query the AZ ID for creating an instance.

URI
---

GET /v2/available-zones

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 1** Response body parameters

   +-----------------------+--------------------------------------------------------------------------------------------------------------+-----------------------+
   | Parameter             | Type                                                                                                         | Description           |
   +=======================+==============================================================================================================+=======================+
   | region_id             | String                                                                                                       | **Definition**        |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | Region ID.            |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | **Constraints**       |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | N/A                   |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | **Range**             |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | N/A                   |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | **Default Value**     |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------------+-----------------------+
   | available_zones       | Array of :ref:`ListAvailableZonesElements <listavailablezones__response_listavailablezoneselements>` objects | **Definition**        |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | Array of AZs.         |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | **Constraints**       |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | N/A                   |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | **Range**             |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | N/A                   |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | **Default Value**     |
   |                       |                                                                                                              |                       |
   |                       |                                                                                                              | N/A                   |
   +-----------------------+--------------------------------------------------------------------------------------------------------------+-----------------------+

.. _listavailablezones__response_listavailablezoneselements:

.. table:: **Table 2** ListAvailableZonesElements

   +-----------------------+-----------------------+-----------------------------------------+
   | Parameter             | Type                  | Description                             |
   +=======================+=======================+=========================================+
   | id                    | String                | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | AZ ID.                                  |
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
   | code                  | String                | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | AZ code.                                |
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
   |                       |                       | AZ name.                                |
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
   | port                  | String                | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | AZ port.                                |
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
   | resource_availability | String                | **Definition**                          |
   |                       |                       |                                         |
   |                       |                       | Whether the AZ has available resources. |
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

Example Requests
----------------

Querying AZ information

.. code-block:: text

   GET https://{endpoint}/v2/available-zones

Example Responses
-----------------

**Status code: 200**

AZ information queried successfully.

.. code-block::

   {
     "region_id" : "xxx",
     "available_zones" : [ {
       "id" : "8c90c2a4e2594c0782faa6b205afeca7",
       "code" : "xxx",
       "name" : "AZ 1",
       "port" : "8002",
       "resource_availability" : "true"
     }, {
       "id" : "d539378ec1314c85b76fefa3f7071458",
       "code" : "xxx",
       "name" : "AZ 2",
       "port" : "8003",
       "resource_availability" : "true",
       "default_az" : false
     }, {
       "id" : "9f1c5806706d4c1fb0eb72f0a9b18c77",
       "code" : "xxx",
       "name" : "AZ 3",
       "port" : "443",
       "resource_availability" : "true"
     } ]
   }

Status Codes
------------

=========== ====================================
Status Code Description
=========== ====================================
200         AZ information queried successfully.
=========== ====================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
