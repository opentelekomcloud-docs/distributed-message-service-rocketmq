:original_name: hrm-pd-010.html

.. _hrm-pd-010:

Restrictions
============

This section describes the restrictions on using DMS for RocketMQ.

.. important::

   Any instability caused by ignorance of the notes and constraints is not covered by the SLA.

Instance
--------

.. table:: **Table 1** Restrictions

   +-----------------------------------+--------------------------------------------------------------------------+
   | Item                              | Restrictions                                                             |
   +===================================+==========================================================================+
   | Version                           | Fixed once the instance is created. Use the same version as your client. |
   +-----------------------------------+--------------------------------------------------------------------------+
   | Storage space                     | -  The disk type cannot be changed once the instance is created.         |
   |                                   | -  Can only be increased.                                                |
   |                                   | -  Can be increased for up to 20 times.                                  |
   +-----------------------------------+--------------------------------------------------------------------------+
   | Broker quantity                   | Can only be increased.                                                   |
   +-----------------------------------+--------------------------------------------------------------------------+
   | VPC/subnet/AZ                     | Fixed once the instance is created.                                      |
   +-----------------------------------+--------------------------------------------------------------------------+
   | Request-Reply                     | Not supported.                                                           |
   +-----------------------------------+--------------------------------------------------------------------------+
   | Configuration parameters          | Cannot be modified using open-source APIs.                               |
   +-----------------------------------+--------------------------------------------------------------------------+

Topic
-----

.. table:: **Table 2** Restrictions

   +-----------------------------------+------------------------------------------------------------------------------------------------------------------+
   | Item                              | Restrictions                                                                                                     |
   +===================================+==================================================================================================================+
   | Maximum number of topics          | Depends on the :ref:`instance specifications <hrm-pd-004>`. This limit cannot be changed.                        |
   |                                   |                                                                                                                  |
   |                                   | When this limit is reached, no more topics can be created.                                                       |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------+
   | Automatic topic creation          | Not supported.                                                                                                   |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------+
   | Broker faults                     | When some brokers of an instance are faulty, topics cannot be created, modified, or deleted, but can be queried. |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------+

Consumer Group
--------------

.. table:: **Table 3** Restrictions

   +----------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------+
   | Item                                               | Restrictions                                                                                                              |
   +====================================================+===========================================================================================================================+
   | Maximum number of consumer groups                  | Depends on the :ref:`instance specifications <hrm-pd-004>`. This limit cannot be changed.                                 |
   |                                                    |                                                                                                                           |
   |                                                    | When this limit is reached, no more consumer groups can be created.                                                       |
   +----------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------+
   | Creating consumer groups, consumers, and producers | Consumer groups, consumers, and producers are generated automatically when you use the instance.                          |
   +----------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------+
   | Consumer offset reset                              | You can reset the retrieval start position to any time within two days.                                                   |
   +----------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------+
   | Resetting the consumer offset                      | Messages may be consumed more than once after the offset is reset.                                                        |
   +----------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------+
   | Broker faults                                      | When some brokers of an instance are faulty, consumer groups cannot be created, modified, or deleted, but can be queried. |
   +----------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------+

Message
-------

.. table:: **Table 4** Restrictions

   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Item                              | Restrictions                                                                                                                                                                                    |
   +===================================+=================================================================================================================================================================================================+
   | Message retention duration        | The default retention period is 48 hours, which can be modified to up to 720 hours. Messages will be automatically deleted after the retention period expires.                                  |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Message size                      | The maximum size of a message is 4 MB. The maximum size of any message attribute (topic name, message type, message ID, or message creation time) is 16 KB. The message size cannot be changed. |
   |                                   |                                                                                                                                                                                                 |
   |                                   | When this limit is reached, messages will fail to be sent.                                                                                                                                      |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Delay of scheduled messages       | The maximum delay is seven days. This limit cannot be changed.                                                                                                                                  |
   |                                   |                                                                                                                                                                                                 |
   |                                   | You can schedule messages to be delivered at any time within seven days.                                                                                                                        |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

User
----

.. table:: **Table 5** Restrictions

   +-----------------+-----------------------------------------------------------------------------------------------------------------+
   | Item            | Restrictions                                                                                                    |
   +=================+=================================================================================================================+
   | Number of users | A maximum of 1000 users can be created for a RocketMQ instance.                                                 |
   +-----------------+-----------------------------------------------------------------------------------------------------------------+
   | Broker faults   | When some brokers of an instance are faulty, users cannot be created, modified, or deleted, but can be queried. |
   +-----------------+-----------------------------------------------------------------------------------------------------------------+
