:original_name: ValidateConsumedMessageForRocketMq.html

.. _ValidateConsumedMessageForRocketMq:

Verifying Consumption
=====================

Function
--------

This API is used to verify consumption.

URI
---

POST /v2/{project_id}/rocketmq/instances/{instance_id}/messages/resend

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

   +-----------------+-----------------+------------------+-----------------------------------+
   | Parameter       | Mandatory       | Type             | Description                       |
   +=================+=================+==================+===================================+
   | group           | Yes             | String           | **Definition**                    |
   |                 |                 |                  |                                   |
   |                 |                 |                  | Group ID.                         |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Constraints**                   |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Range**                         |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Default Value**                 |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   +-----------------+-----------------+------------------+-----------------------------------+
   | topic           | No              | String           | **Definition**                    |
   |                 |                 |                  |                                   |
   |                 |                 |                  | Topic to which a message belongs. |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Constraints**                   |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Range**                         |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Default Value**                 |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   +-----------------+-----------------+------------------+-----------------------------------+
   | client_id       | Yes             | String           | **Definition**                    |
   |                 |                 |                  |                                   |
   |                 |                 |                  | Client ID.                        |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Constraints**                   |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Range**                         |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Default Value**                 |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   +-----------------+-----------------+------------------+-----------------------------------+
   | msg_id_list     | No              | Array of strings | **Definition**                    |
   |                 |                 |                  |                                   |
   |                 |                 |                  | Message list.                     |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Constraints**                   |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Range**                         |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   |                 |                 |                  |                                   |
   |                 |                 |                  | **Default Value**                 |
   |                 |                 |                  |                                   |
   |                 |                 |                  | N/A                               |
   +-----------------+-----------------+------------------+-----------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------+------------------------------------------------------------------------------------------------------+----------------------------------+
   | Parameter             | Type                                                                                                 | Description                      |
   +=======================+======================================================================================================+==================================+
   | resend_results        | Array of :ref:`resend_results <validateconsumedmessageforrocketmq__response_resend_results>` objects | **Definition**                   |
   |                       |                                                                                                      |                                  |
   |                       |                                                                                                      | Consumption verification result. |
   |                       |                                                                                                      |                                  |
   |                       |                                                                                                      | **Constraints**                  |
   |                       |                                                                                                      |                                  |
   |                       |                                                                                                      | N/A                              |
   |                       |                                                                                                      |                                  |
   |                       |                                                                                                      | **Range**                        |
   |                       |                                                                                                      |                                  |
   |                       |                                                                                                      | N/A                              |
   |                       |                                                                                                      |                                  |
   |                       |                                                                                                      | **Default Value**                |
   |                       |                                                                                                      |                                  |
   |                       |                                                                                                      | N/A                              |
   +-----------------------+------------------------------------------------------------------------------------------------------+----------------------------------+

.. _validateconsumedmessageforrocketmq__response_resend_results:

.. table:: **Table 4** resend_results

   +-----------------------+-----------------------+-----------------------+
   | Parameter             | Type                  | Description           |
   +=======================+=======================+=======================+
   | msg_id                | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Message ID.           |
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
   | error_code            | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Error code.           |
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
   | error_message         | String                | **Definition**        |
   |                       |                       |                       |
   |                       |                       | Error message.        |
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

Verifying consumption

.. code-block:: text

   POST https://{endpoint}/v2/{project_id}/rocketmq/instances/{instance_id}/messages/resend

   {
     "group" : "GID_test",
     "client_id" : "192.168.0.1",
     "msg_id_list" : [ "id1" ]
   }

Example Responses
-----------------

**Status code: 200**

Consumption verified.

.. code-block::

   {
     "resend_results" : [ {
       "msg_id" : "C0A8149E0000277600000000000B6835",
       "error_code" : "DMS.00000000",
       "error_message" : "Success."
     } ]
   }

Status Codes
------------

=========== =====================
Status Code Description
=========== =====================
200         Consumption verified.
=========== =====================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
