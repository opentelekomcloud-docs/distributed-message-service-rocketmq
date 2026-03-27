:original_name: hrm-ug-066.html

.. _hrm-ug-066:

Process of Using RocketMQ
=========================

Distributed Message Service (DMS) for RocketMQ is message-oriented middleware that delivers low latency, high flexibility, high throughput, dynamic expansion, easy management, and abundant messaging functions. Users can create RocketMQ instances. Producer clients can access RocketMQ instances for message production. The produced messages are stored in topics of RocketMQ instances. Consumer clients can subscribe to topics to consume messages.

The following figure shows the process of using a RocketMQ instance to produce and consume messages.


.. figure:: /_static/images/en-us_image_0000001960110865.png
   :alt: **Figure 1** Process of using RocketMQ

   **Figure 1** Process of using RocketMQ

#. :ref:`Creating an IAM User and Granting DMS for RocketMQ Permissions <hrm-ug-030>`

   Create IAM users and grant them only the DMS for RocketMQ permissions required to perform a given task based on their job responsibilities.

#. :ref:`Creating a RocketMQ Instance <hrm-ug-002>`

   RocketMQ instances are physically isolated and exclusively occupied by each tenant.

#. :ref:`Creating a RocketMQ Topic <hrm-ug-008>`

   Create a topic for storing messages so that producers can produce messages and consumers can subscribe to messages.

#. :ref:`Accessing an Instance <hrm-ug-041>`

   The client connects to RocketMQ instances over a private or public network, and produces and consumes messages.
