:original_name: hrm-ug-021.html

.. _hrm-ug-021:

Viewing RocketMQ Audit Logs
===========================

Cloud Trace Service (CTS) records DMS for RocketMQ operations. You can query, audit, and backtrack them later.

Prerequisite
------------

CTS has been enabled.

DMS for RocketMQ Operations Supported by CTS
--------------------------------------------

.. table:: **Table 1** Operations logged by CTS

   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Operation                                                                | Resource Type | Trace Name                             |
   +==========================================================================+===============+========================================+
   | Successfully creating a topic                                            | reliability   | RocketMQ_Topic_CreationSuccess         |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to create a topic                                                | reliability   | RocketMQ_Topic_CreationFailure         |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully modifying a topic                                           | reliability   | RocketMQ_Topic_ModifySuccess           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to modify a topic                                                | reliability   | RocketMQ_Topic_ModifyFailure           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully deleting a topic                                            | reliability   | RocketMQ_Topic_DeletionSuccess         |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to delete a topic                                                | reliability   | RocketMQ_Topic_DeletionFailure         |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully deleting topics in batches                                  | reliability   | RocketMQ_Batch_Topic_DeletionSuccess   |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to delete topics in batches                                      | reliability   | RocketMQ_Batch_Topic_DeletionFailure   |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully modifying topics in batches                                 | reliability   | RocketMQ_Batch_Topic_ModifySuccess     |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to modify topics in batches                                      | reliability   | RocketMQ_Batch_Topic_ModifyFailure     |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully creating a consumer group                                   | reliability   | RocketMQ_Create_GroupSuccess           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to create a consumer group                                       | reliability   | RocketMQ_Create_GroupFailure           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully editing a consumer group                                    | reliability   | RocketMQ_Group_ModifySuccess           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to edit a consumer group                                         | reliability   | RocketMQ_Group_ModifyFailure           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully deleting a consumer group                                   | reliability   | RocketMQ_Group_DeletionSuccess         |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to delete a consumer group                                       | reliability   | RocketMQ_Group_DeletionFailure         |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully deleting consumer groups in batches                         | reliability   | RocketMQ_Batch_Group_DeletionSuccess   |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to delete consumer groups in batches                             | reliability   | RocketMQ_Batch_Group_DeletionFailure   |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully editing consumer groups in batches                          | reliability   | RocketMQ_Batch_Group_ModifySuccess     |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to edit consumer groups in batches                               | reliability   | RocketMQ_Batch_Group_ModifyFailure     |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully restarting an instance node                                 | reliability   | restartInstanceBrokerSuccess           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to restart an instance node                                      | reliability   | restartInstanceBrokerFailure           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully deleting a background task                                  | reliability   | deleteDMSBackendJobSuccess             |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to delete a background task                                      | reliability   | deleteDMSBackendJobFailure             |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully submitting a request to scale up an instance                | reliability   | extendDMSInstanceSuccess               |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to submit a request to scale up an instance                      | reliability   | extendDMSInstanceFailure               |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully deleting an instance that failed to be created              | reliability   | deleteDMSCreateFailureInstancesSuccess |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to delete an instance that failed to be created                  | reliability   | deleteDMSCreateFailureInstancesFailure |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully submitting a request to delete multiple instances at a time | reliability   | batchDeleteDMSInstanceSuccess          |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to submit a request to delete multiple instances at a time       | reliability   | batchDeleteDMSInstanceFailure          |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully submitting a request to modify instance information         | reliability   | modifyDMSInstanceInfoSuccess           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to submit a request to modify instance information               | reliability   | modifyDMSInstanceInfoFailure           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Deleting multiple instance tasks at a time                               | reliability   | batchDeleteDMSInstanceTask             |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully deleting an instance                                        | reliability   | deleteDMSInstanceTaskSuccess           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to delete an instance                                            | reliability   | deleteDMSInstanceTaskFailure           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully creating an instance                                        | reliability   | createDMSInstanceTaskSuccess           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to create an instance                                            | reliability   | createDMSInstanceTaskFailure           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully scaling up an instance                                      | reliability   | extendDMSInstanceTaskSuccess           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to scale up an instance                                          | reliability   | extendDMSInstanceTaskFailure           |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Successfully modifying instance information                              | reliability   | modifyDMSInstanceInfoTaskSuccess       |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+
   | Failing to modify instance information                                   | reliability   | modifyDMSInstanceInfoTaskFailure       |
   +--------------------------------------------------------------------------+---------------+----------------------------------------+

Viewing Audit Logs
------------------

See `Querying Real-Time Traces <https://docs.otc.t-systems.com/en-us/usermanual/cts/en-us_topic_0030598499.html>`__.
