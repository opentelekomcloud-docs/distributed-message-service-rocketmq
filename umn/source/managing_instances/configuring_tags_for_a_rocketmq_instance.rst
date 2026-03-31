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


Configuring Tags for a RocketMQ Instance
----------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the DMS for RocketMQ page.

#. Configure RocketMQ instance tags on the **Edit Tag** page in any of the following ways:

   -  In the row containing the desired RocketMQ instance, choose **More** > **Edit Tag**.
   -  Click a RocketMQ instance name to go to the instance overview page. In the navigation pane, choose **Instance** > **Tags**.
   -  Click a RocketMQ instance name to go to the instance overview page. In the upper right corner, choose |image3| > **Edit Tag**.

#. Add, edit, or delete tags as required.

   .. table:: **Table 2** Tag operations

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                         | Procedure                                                                                                                                                           |
      +===================================+=====================================================================================================================================================================+
      | Adding a tag                      | a. Click **Add Tag** to set tags with **Tag key** and **Tag value**. If you have predefined tags, select a predefined pair of tag key and value, and click **Add**. |
      |                                   |                                                                                                                                                                     |
      |                                   |    A maximum of **20 tags** can be added.                                                                                                                           |
      |                                   |                                                                                                                                                                     |
      |                                   | b. Click **OK**.                                                                                                                                                    |
      |                                   |                                                                                                                                                                     |
      |                                   |    View the new tag on the **Edit Tag** or tag list page.                                                                                                           |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Editing a tag                     | Modify the tag key and value, and click **OK**.                                                                                                                     |
      |                                   |                                                                                                                                                                     |
      |                                   | View the edited tag on the **Edit Tag** or tag list page.                                                                                                           |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Deleting a tag                    | In the row containing the tag to be deleted, click **Delete**. Then, click **OK** to delete the tag.                                                                |
      |                                   |                                                                                                                                                                     |
      |                                   | The tags are deleted when they are no longer displayed on the **Edit Tag** page and tag list.                                                                       |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0000002435187988.png
