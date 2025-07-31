:original_name: hrm-ug-072.html

.. _hrm-ug-072:

RocketMQ Metadata Migration Overview
====================================

RocketMQ metadata contains topics and consumer groups excluding message production or consumption records. To use the original topics and consumer groups, migrate their metadata to a specified RocketMQ instance, without the need of manual creation.

RocketMQ service migration involves the following scenarios:

-  Migrating RocketMQ instance metadata from others, which includes:

   -  Metadata of others' RocketMQ
   -  Metadata of self-hosted RocketMQ instance
   -  Metadata of another cloud RocketMQ instance

-  Migrating RocketMQ instance metadata from RabbitMQ
