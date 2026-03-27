:original_name: hrm-pd-008.html

.. _hrm-pd-008:

RocketMQ Concepts
=================

Topic
-----

A topic is a category of messages. It is the basic unit for creating and retrieving messages.

Queue
-----

A topic consists of multiple queues. A larger number of queues indicates higher retrieval concurrency.

Producer
--------

A producer sends messages to the server.

Producer Group
--------------

Producers in a group send the same type of messages with the same logic.

Consumer
--------

A consumer obtains messages from the server.

Consumer Group
--------------

A consumer group contains consumers that have similar retrieval behavior.

Broker
------

Brokers are a cluster of ECSs that process services.

NameServer
----------

A lightweight registry that stores metadata. Before producing or consuming messages, producers and consumers must obtain metadata from a NameServer.
