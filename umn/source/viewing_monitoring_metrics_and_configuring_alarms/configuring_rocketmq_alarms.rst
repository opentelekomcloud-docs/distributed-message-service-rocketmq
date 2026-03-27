:original_name: hrm-ug-043.html

.. _hrm-ug-043:

Configuring RocketMQ Alarms
===========================

This section describes the alarm policies of some metrics and how to configure them. In actual services, you are advised to configure alarm rules for metrics based on the following alarm policies.

.. note::

   **Approach Upper Limit** in the following table indicates whether the threshold is close to the upper limit of the performance supported by current resources. If the threshold is close to the upper limit and usage continues to rise, services may be abnormal.

.. table:: **Table 1** RocketMQ instance metrics to configure alarm rules for

   +---------------------------+--------------+----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Metric Name               | Normal Range | Alarm Policy                     | Approach Upper Limit | Metric Description and Alarm Handling Suggestions                                                                                                                                                                                                   |
   +===========================+==============+==================================+======================+=====================================================================================================================================================================================================================================================+
   | Disk Capacity Usage       | 0-100        | Alarm threshold: Raw data > 85   | Yes                  | **Metric description:** disk usage of the RocketMQ VM. Unit: %                                                                                                                                                                                      |
   |                           |              |                                  |                      |                                                                                                                                                                                                                                                     |
   |                           |              | Number of consecutive periods: 3 |                      | **Handling suggestion**: If an alarm is generated for this metric, the current instance specifications are insufficient to carry services. The **storage space** needs to be expanded by referring to :ref:`Modifying Specifications <hrm-ug-038>`. |
   |                           |              |                                  |                      |                                                                                                                                                                                                                                                     |
   |                           |              | Alarm severity: Critical         |                      |                                                                                                                                                                                                                                                     |
   +---------------------------+--------------+----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Average Load per CPU Core | 0-2          | Alarm threshold: Raw data > 1.5  | Yes                  | **Metric description:** average load of each CPU core of the RocketMQ VM.                                                                                                                                                                           |
   |                           |              |                                  |                      |                                                                                                                                                                                                                                                     |
   |                           |              | Number of consecutive periods: 3 |                      | **Handling suggestion**: If an alarm is generated for this metric, perform the following operations:                                                                                                                                                |
   |                           |              |                                  |                      |                                                                                                                                                                                                                                                     |
   |                           |              | Alarm severity: Major            |                      | #. Add brokers by referring to :ref:`Modifying Specifications <hrm-ug-038>`.                                                                                                                                                                        |
   |                           |              |                                  |                      | #. Redeploy existing topics to the new brokers by referring to :ref:`Modifying RocketMQ Topic Configurations <hrm-ug-010>`.                                                                                                                         |
   +---------------------------+--------------+----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Memory Usage              | 0-100        | Alarm threshold: Raw data > 85   | Yes                  | **Metric description:** memory usage of the RocketMQ VM. Unit: %                                                                                                                                                                                    |
   |                           |              |                                  |                      |                                                                                                                                                                                                                                                     |
   |                           |              | Number of consecutive periods: 3 |                      | **Handling suggestion**: If an alarm is generated for this metric, perform the following operations:                                                                                                                                                |
   |                           |              |                                  |                      |                                                                                                                                                                                                                                                     |
   |                           |              | Alarm severity: Critical         |                      | #. Add brokers by referring to :ref:`Modifying Specifications <hrm-ug-038>`.                                                                                                                                                                        |
   |                           |              |                                  |                      | #. Redeploy existing topics to the new brokers by referring to :ref:`Modifying RocketMQ Topic Configurations <hrm-ug-010>`.                                                                                                                         |
   +---------------------------+--------------+----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+


Configuring RocketMQ Alarms
---------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. In the row containing the desired instance, click **View Metric**.

   You are redirected to the metric monitoring page on the Cloud Eye console.

#. Hover the mouse pointer over a metric and click |image3| to create an alarm rule for the metric.

   The **Create Alarm Rule** page is displayed.

#. Specify the alarm rule details.

   For details, see `Creating Alarm Rules <https://docs.otc.t-systems.com/en-us/usermanual/ces/ces_01_0073.html>`__.

   a. Enter the alarm name and description.
   b. Specify the alarm policy and alarm severity.
   c. Set the alarm notification configurations. If you enable **Alarm Notification**, set the validity period, notification object, and trigger condition.
   d. Click **Create**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0000001160616010.png
