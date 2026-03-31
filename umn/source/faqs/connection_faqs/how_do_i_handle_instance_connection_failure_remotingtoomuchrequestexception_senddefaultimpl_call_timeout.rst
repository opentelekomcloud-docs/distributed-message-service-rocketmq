:original_name: hrm_faq_023.html

.. _hrm_faq_023:

How Do I Handle Instance Connection Failure "RemotingTooMuchRequestException: sendDefaultImpl call timeout"
===========================================================================================================

Symptom
-------

Connecting to a RocketMQ instance failed. The error message is "RemotingTooMuchRequestException: sendDefaultImpl call timeout".

Possible Cause
--------------

The security group does not allow the service port.

Solution
--------

#. Log in to the console.

#. Click |image1| in the upper left corner of the console and select a region.

   Select a region near you to ensure the lowest latency possible.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Click a RocketMQ instance name to go to the instance overview page.

#. .. _hrm_faq_023__li5890738101920:

   Obtain the port in **Allow Access To** in the **Network** area.

#. Click the security group name to go to the security group details page.

#. Add an inbound rule to allow the port obtained in :ref:`5 <hrm_faq_023__li5890738101920>`.

.. |image1| image:: /_static/images/en-us_image_0000002506403071.png
.. |image2| image:: /_static/images/en-us_image_0000002474323040.png
