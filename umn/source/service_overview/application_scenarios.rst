:original_name: hrm-pd-003.html

.. _hrm-pd-003:

Application Scenarios
=====================

E-Commerce
----------

E-commerce applications face the following challenges:

-  E-commerce applications usually involve order placement, payment, and notification processing. Multiple service systems work together to complete a task, and upper-layer service systems depend on lower-layer service systems. If there are a large number of layers, the performance of user-facing services will deteriorate, affecting user experience.
-  During e-commerce shopping events, service systems that provide subscription-based notifications are required.

DMS for RocketMQ can help you cope with e-commerce challenges.

-  DMS for RocketMQ decouples service systems to improve their processing capabilities and response speeds.
-  DMS for RocketMQ allows for scheduled and delayed message delivery to meet the requirements for subscription-based notifications.

|image1|

Finance
-------

Unlike traditional finance, Internet finance requires fast responses to the rapidly changing Internet landscape. Common functions in traditional finance are extracted and then packaged into microservice modules to form a middle platform which provides basic capabilities for upper-layer service systems. With its decoupling and linking advantages, DMS for RocketMQ improves the processing capability and response speed of each microservice module, playing an indispensable role in the service middle platform.

|image2|

IoT
---

Massive device access is typical in IoT scenarios. A massive number of devices bring in massive amounts of data. However, each service component only desires specific data. Therefore, it is important to quickly identify data that services desire from a large amount of data. To address this challenge, DMS for RocketMQ provides message filtering. When sent from devices, messages are tagged to specify the message type. Services can specify only the desired types of messages to retrieve.

|image3|

.. |image1| image:: /_static/images/en-us_image_0000001159630546.png
.. |image2| image:: /_static/images/en-us_image_0000001159311966.png
.. |image3| image:: /_static/images/en-us_image_0000001204870247.png
