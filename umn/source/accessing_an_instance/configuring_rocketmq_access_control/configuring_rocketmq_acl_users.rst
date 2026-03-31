:original_name: hrm-ug-035.html

.. _hrm-ug-035:

Configuring RocketMQ ACL Users
==============================

To produce and consume messages to RocketMQ instances with ACL enabled, add ACL users. You can create multiple users and assign different topic and consumer group permissions to them.

Prerequisites
-------------

-  A RocketMQ instance has been created.
-  :ref:`ACL <hrm-ug-070>` has been enabled.

.. _hrm-ug-035__section491614421020:

Creating a User
---------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Users**.

#. Click **Create User**.

#. Configure the user's name and other parameters by referring to :ref:`Table 1 <hrm-ug-035__table116771410124010>`.

   .. _hrm-ug-035__table116771410124010:

   .. table:: **Table 1** User parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================================================+
      | Name                              | Name of the user.                                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                         |
      |                                   | A username must meet the following requirements:                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                         |
      |                                   | -  Contains 7 to 64 characters.                                                                                                                                                                         |
      |                                   | -  Only letters, digits, hyphens (-), and underscores (_) are allowed. The value must start with a letter.                                                                                              |
      |                                   | -  The name must be unique.                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                         |
      |                                   | The name cannot be changed after the user is created.                                                                                                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | IP Whitelist                      | Users from whitelisted IP addresses have publish/subscribe permissions for all topics and consumer groups, and their secret keys will not be verified.                                                  |
      |                                   |                                                                                                                                                                                                         |
      |                                   | The IP whitelist can be set to specific IP addresses or network segments.                                                                                                                               |
      |                                   |                                                                                                                                                                                                         |
      |                                   | -  Use commas (,) to separate multiple IP addresses, for example, **192.168.1.2,192.168.2.3**.                                                                                                          |
      |                                   | -  IP network segment, for example, **192.*.*.\***.                                                                                                                                                     |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Administrator                     | **Enabled by default and fixed for the 5.x basic edition.**                                                                                                                                             |
      |                                   |                                                                                                                                                                                                         |
      |                                   | A user configured as the administrator will have publish and subscribe permissions for all topics, and the subscribe permission for consumer groups.                                                    |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Secret Key                        | The user's secret key.                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                         |
      |                                   | The key setting rules are as follows:                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                         |
      |                                   | -  Contains 8 to 32 characters.                                                                                                                                                                         |
      |                                   | -  Cannot start with "-", contains at least three types of the following characters: uppercase letters, lowercase letters, digits, and special characters :literal:`\`~!@#$%^&*()-_=+\\|[{}];:'",<.>/?` |
      |                                   | -  Cannot be the username or the username spelled backwards.                                                                                                                                            |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

Accessing the Server as a User
------------------------------

After ACL is enabled for an instance, user authentication information must be added to both the producer and consumer configurations. To enable ACL using Java, Go, or Python, refer to the following documents:

-  Section "Java" > "Controlling Access with ACL" in *Distributed Message Service for RocketMQ Developer Guide*
-  Section "Go" > "Controlling Access with ACL" in Distributed Message Service for RocketMQ Developer Guide
-  Section "Python" > "Controlling Access with ACL" in Distributed Message Service for RocketMQ Developer Guide

Modifying User Information
--------------------------

#. Log in to the console.

#. Click |image3| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image4| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Users**.

#. In the row containing the desired user, click **Edit**.

#. Modify the user information as required.

   Usernames cannot be changed. For other parameters, see :ref:`Table 1 <hrm-ug-035__table116771410124010>`.

#. Click **OK**.

Exporting Users
---------------

#. Log in to the console.

#. Click |image5| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image6| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Users**.

#. Export the user list in either of the following ways:

   -  Select the desired users and choose **Export** > **Export selected data to an XLSX file** to export specified users.
   -  Choose **Export** > **Export all data to an XLSX file** to export all users.

Deleting a User
---------------

Deleting a user will remove its authorization relationship and disconnect it from the instance.

#. Log in to the console.

#. Click |image7| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image8| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Users**.

#. In the row containing the desired user, click **Delete**.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0143929918.png
.. |image4| image:: /_static/images/en-us_image_0000001143589128.png
.. |image5| image:: /_static/images/en-us_image_0143929918.png
.. |image6| image:: /_static/images/en-us_image_0000001143589128.png
.. |image7| image:: /_static/images/en-us_image_0143929918.png
.. |image8| image:: /_static/images/en-us_image_0000001143589128.png
