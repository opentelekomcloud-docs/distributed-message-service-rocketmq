:original_name: ListConfigFeatures.html

.. _ListConfigFeatures:

Obtaining the Feature Switch List
=================================

Function
--------

This API is used to obtain the feature switch list.

URI
---

GET /v2/config/features

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 1** Response body parameters

   +-----------------------+----------------------------------------------------------------------------------------------+---------------------------+
   | Parameter             | Type                                                                                         | Description               |
   +=======================+==============================================================================================+===========================+
   | features              | Array of :ref:`ListConfigFeatures <listconfigfeatures__response_listconfigfeatures>` objects | **Definition**            |
   |                       |                                                                                              |                           |
   |                       |                                                                                              | Feature list.             |
   +-----------------------+----------------------------------------------------------------------------------------------+---------------------------+
   | totalRecord           | Integer                                                                                      | **Definition**            |
   |                       |                                                                                              |                           |
   |                       |                                                                                              | Total number of features. |
   |                       |                                                                                              |                           |
   |                       |                                                                                              | **Range**                 |
   |                       |                                                                                              |                           |
   |                       |                                                                                              | N/A                       |
   +-----------------------+----------------------------------------------------------------------------------------------+---------------------------+

.. _listconfigfeatures__response_listconfigfeatures:

.. table:: **Table 2** ListConfigFeatures

   +-----------------------+-----------------------+--------------------------------+
   | Parameter             | Type                  | Description                    |
   +=======================+=======================+================================+
   | featureId             | String                | **Definition**                 |
   |                       |                       |                                |
   |                       |                       | Feature ID.                    |
   |                       |                       |                                |
   |                       |                       | **Range**                      |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   +-----------------------+-----------------------+--------------------------------+
   | status                | Integer               | **Definition**                 |
   |                       |                       |                                |
   |                       |                       | Status.                        |
   |                       |                       |                                |
   |                       |                       | **Constraints**                |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   |                       |                       |                                |
   |                       |                       | **Range**                      |
   |                       |                       |                                |
   |                       |                       | -  **true**: feature enabled   |
   |                       |                       |                                |
   |                       |                       | -  **false**: feature disabled |
   +-----------------------+-----------------------+--------------------------------+
   | description           | String                | **Definition**                 |
   |                       |                       |                                |
   |                       |                       | Feature description.           |
   |                       |                       |                                |
   |                       |                       | **Range**                      |
   |                       |                       |                                |
   |                       |                       | N/A                            |
   +-----------------------+-----------------------+--------------------------------+

Example Requests
----------------

.. code-block:: text

   GET https://{endpoint}/v2/config/features

Example Responses
-----------------

**Status code: 200**

Queried.

.. code-block::

   {
     "features" : [ {
       "featureId" : "rocketmq_cross_vpc",
       "status" : 0,
       "description" : "rocketmq cross vpc switch"
     }, {
       "featureId" : "pdp5_auth_enable",
       "status" : 1,
       "description" : "pdp5 check permission enable"
     } ],
     "totalRecord" : 2
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
