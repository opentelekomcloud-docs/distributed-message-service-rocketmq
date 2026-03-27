:original_name: hrm_faq_014.html

.. _hrm_faq_014:

Why Can't I View RocketMQ Monitoring Data?
==========================================

-  A percent (%) or vertical bar (|) contained in a topic name will be converted to an underscore (_) by Cloud Eye. For example, if a topic name is **test%01**, it will be displayed as **test_01** on Cloud Eye.
-  If the name of a monitored object contains periods (.), the object may not be displayed on Cloud Eye because its name exceeds the length limit. On Cloud Eye, a period (.) counts as five characters. The total dimension length must be within 256 characters.
