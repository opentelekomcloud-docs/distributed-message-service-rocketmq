:original_name: hrm_faq_029.html

.. _hrm_faq_029:

Does RocketMQ Support Throttling?
=================================

Throttling is triggered under the following circumstances:

#. There are many message production and consumption requests within a short period of time.

#. A request may be limited at a second when traffic bursts at the second.

   The monitoring collects the average TPS within one minute instead of specific seconds.

When a request is limited, the message production fails and the server returns error code 215. Ensure that the production and consumption TPS are within the instance specifications.
