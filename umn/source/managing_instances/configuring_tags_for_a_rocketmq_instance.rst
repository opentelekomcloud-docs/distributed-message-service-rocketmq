:original_name: hrm-ug-058.html

.. _hrm-ug-058:

Configuring Tags for a RocketMQ Instance
========================================

Tags facilitate RocketMQ instance identification and management.

You can add tags to a RocketMQ instance when creating the instance or add tags on the **Tags** tab page of the created instance. You can also delete tags that are no longer used.

A tag consists of a tag key and a tag value. :ref:`Table 1 <hrm-ug-058__table193611920984>` lists the tag key and value requirements.

.. _hrm-ug-058__table193611920984:

.. table:: **Table 1** Tag key and value requirements

   +-----------------------------------+-----------------------------------------------------------------------------+
   | Parameter                         | Requirement                                                                 |
   +===================================+=============================================================================+
   | Tag key                           | -  Cannot be left blank.                                                    |
   |                                   | -  Must be unique for the same instance.                                    |
   |                                   | -  Can contain 1 to 128 characters.                                         |
   |                                   | -  Can contain letters, digits, spaces, and special characters \_.:=+-@     |
   |                                   | -  Cannot start or end with a space.                                        |
   |                                   | -  Cannot start with **\_sys\_**.                                           |
   +-----------------------------------+-----------------------------------------------------------------------------+
   | Tag value                         | -  Can contain 0 to 255 characters.                                         |
   |                                   | -  Can contain letters, digits, spaces, and special characters ``_.:/=+-@`` |
   |                                   | -  Cannot start or end with a space in instance creation.                   |
   +-----------------------------------+-----------------------------------------------------------------------------+

Notes and Constraints
---------------------

A maximum of 20 tags can be added.

Prerequisite
------------

A RocketMQ instance has been created.

Adding and Deleting Tags
------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click an instance name to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Tags**.

#. Perform the following operations as required:

   -  Add a tag

      a. Click **Edit Tag**.

      b. Click **Add Tag** to set tags with **Tag key** and **Tag value**.

         You can repeat this step to add up to 20 tags.

         If you have predefined tags, select predefined tag keys and values, and click **Add**.

      c. Click **OK**.

   -  Delete a tag

      a. Click **Edit Tag**.
      b. Click **Delete** next to the tag to be deleted.
      c. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
