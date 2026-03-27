:original_name: hrm-ug-058.html

.. _hrm-ug-058:

Configuring Tags for a RocketMQ Instance
========================================

Tags facilitate RocketMQ instance identification and management.

You can add tags to a RocketMQ instance when creating the instance or add tags on the **Tags** tab page of the created instance. Up to 20 tags can be added to an instance. Tags can be deleted.

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
   +-----------------------------------+-----------------------------------------------------------------------------+

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

#. In the navigation pane, choose **Tags**.

   View the tags of the instance.

#. Perform the following operations as required:

   -  Add a tag

      a. Click **Create/Edit Tag**.

      b. Enter a tag key and a tag value, and click **Add**.

         If you have predefined tags, select a predefined pair of tag key and value, and click **Add**.

      c. Click **OK**.

   -  Delete a tag

      Delete a tag in any of the following ways:

      -  In the row containing the tag to be deleted, click **Delete**. Click **OK**.

      -  Click **Create/Edit Tag**. In the dialog box that is displayed, click |image3| next to the tag to be deleted and click **OK**.

         You can delete up to 19 tags in this way.

      -  To delete tags in batches, select the tags, click **Delete** on the upper left, and click **OK**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0000002313114012.png
