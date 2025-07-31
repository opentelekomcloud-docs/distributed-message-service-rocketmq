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

#. .. _hrm_faq_023__li1605183417015:

   On the instance details page of the RocketMQ console, view the port next to **Network** > **Allow Access To**.

#. Click the security group name to go to the security group details page.

#. Add an inbound rule to allow the port obtained in :ref:`1 <hrm_faq_023__li1605183417015>`.
