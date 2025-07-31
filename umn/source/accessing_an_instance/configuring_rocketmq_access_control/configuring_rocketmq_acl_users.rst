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

#. In the navigation pane, choose **Users**.

#. Click **Create User**.

#. Configure the user's name and other parameters by referring to :ref:`Table 1 <hrm-ug-035__table116771410124010>`.

   .. _hrm-ug-035__table116771410124010:

   .. table:: **Table 1** User parameters

      +------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                          | Description                                                                                                                                                                                                                                                                                                                      |
      +====================================+==================================================================================================================================================================================================================================================================================================================================+
      | Name                               | Name of the user.                                                                                                                                                                                                                                                                                                                |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | A username must meet the following requirements:                                                                                                                                                                                                                                                                                 |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | -  Contains 7 to 64 characters.                                                                                                                                                                                                                                                                                                  |
      |                                    | -  Only letters, digits, hyphens (-), and underscores (_) are allowed. The value must start with a letter.                                                                                                                                                                                                                       |
      |                                    | -  The name must be unique.                                                                                                                                                                                                                                                                                                      |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | The name cannot be changed after the user is created.                                                                                                                                                                                                                                                                            |
      +------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | IP Whitelist                       | Users from whitelisted IP addresses have publish/subscribe permissions for all topics and consumer groups, and their secret keys will not be verified.                                                                                                                                                                           |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | The IP whitelist can be set to specific IP addresses or network segments.                                                                                                                                                                                                                                                        |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | -  Use commas (,) to separate multiple IP addresses, for example, **192.168.1.2,192.168.2.3**.                                                                                                                                                                                                                                   |
      |                                    | -  IP network segment, for example, **192.*.*.\***.                                                                                                                                                                                                                                                                              |
      +------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Default Topic Permissions          | Specifies the default topic permission of a user.                                                                                                                                                                                                                                                                                |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | Options:                                                                                                                                                                                                                                                                                                                         |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | -  **None**: The topic is disabled.                                                                                                                                                                                                                                                                                              |
      |                                    | -  **Publish**: Users can only send messages to the topic.                                                                                                                                                                                                                                                                       |
      |                                    | -  **Subscribe**: Users can only consume messages from the topic.                                                                                                                                                                                                                                                                |
      |                                    | -  **Publish/Subscribe**: Users can send messages to or consume them from the topic.                                                                                                                                                                                                                                             |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | The default permissions will be overwritten by the permissions configured for specific topics, if any. For example, if **Default Topic Permissions** is set to **Subscribe**, but a topic is configured with the **Publish/Subscribe** permissions, the topic's actual permissions will be **Publish/Subscribe**.                |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | Unavailable for v5.x basic edition.                                                                                                                                                                                                                                                                                              |
      +------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Default Consumer Group Permissions | Specifies the default consumer group permission of a user.                                                                                                                                                                                                                                                                       |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | Options:                                                                                                                                                                                                                                                                                                                         |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | -  **None**: the consumer group is disabled.                                                                                                                                                                                                                                                                                     |
      |                                    | -  **Subscribe**: The consumer group is enabled.                                                                                                                                                                                                                                                                                 |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | The default permissions will be overwritten by the permissions configured for specific consumer groups, if any. For example, if a consumer group is configured with the **None** permissions, the user will not have permissions for the consumer group, even if **Default Consumer Group Permissions** is set to **Subscribe**. |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | Unavailable for v5.x basic edition.                                                                                                                                                                                                                                                                                              |
      +------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Secret Key                         | The user's secret key.                                                                                                                                                                                                                                                                                                           |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | The key setting rules are as follows:                                                                                                                                                                                                                                                                                            |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | -  Contains 8 to 32 characters.                                                                                                                                                                                                                                                                                                  |
      |                                    | -  Cannot start with "-", contains at least three types of the following characters: uppercase letters, lowercase letters, digits, and special characters :literal:`\`~!@#$%^&*()-_=+\\|[{}];:'",<.>/?`                                                                                                                          |
      |                                    | -  Cannot be the username or the username spelled backwards.                                                                                                                                                                                                                                                                     |
      +------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Administrator                      | A user configured as the administrator will have publish/subscribe permissions for all topics and consumer groups.                                                                                                                                                                                                               |
      |                                    |                                                                                                                                                                                                                                                                                                                                  |
      |                                    | Unavailable for v5.x basic edition.                                                                                                                                                                                                                                                                                              |
      +------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

(Optional) Assigning Topic or Consumer Group Permissions to a User
------------------------------------------------------------------

Users are created with default topic and consumer group permissions. To modify the default permissions, reset them here. By default, the administrator has all permissions.

**Unavailable for v5.x basic edition.**

#. Click a user to go to the user details page.

#. On the **Topic Permissions** or **Consumer Group Permissions** tab page, click **Add**.

#. Select desired topics or consumer groups, select the required permissions, and click **OK**.

   These permissions overwrite the default permissions. For example, in :ref:`Figure 1 <hrm-ug-035__fig02161358114311>`, users finally have publish/subscribe permissions for topic **test01**.

   .. _hrm-ug-035__fig02161358114311:

   .. figure:: /_static/images/en-us_image_0000002241746861.png
      :alt: **Figure 1** User details page

      **Figure 1** User details page

   .. note::

      The following operations can also be performed on the **Topic Permissions** or **Consumer Group Permissions** tab page.

      -  Exporting the topic or consumer group list: Choose **Export** > **Export all data to an XLSX file** or **Export** > **Export selected data to an XLSX file**.
      -  Deleting topics or consumer groups in either of the following ways:

         -  In the row containing the topic or consumer group to be deleted, click **Delete**.
         -  Select the topics or consumer groups to be deleted and click **Delete** in the upper left corner.

Accessing the Server as a User
------------------------------

After ACL is enabled for an instance, user authentication information must be added to both the producer and consumer configurations. For details, see the following instructions:

-  Section "Java" > "Controlling Access with ACL" in *Distributed Message Service for RocketMQ Developer Guide*
-  Section "Go" > "Controlling Access with ACL" in Distributed Message Service for RocketMQ Developer Guide
-  Section "Python" > "Controlling Access with ACL" in Distributed Message Service for RocketMQ Developer Guide

Modifying User Information
--------------------------

#. Log in to the console.

#. Click |image3| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image4| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Users**.

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

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Users**.

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

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Users**.

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
