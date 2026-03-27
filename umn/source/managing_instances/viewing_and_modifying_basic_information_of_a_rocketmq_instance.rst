:original_name: hrm-ug-004.html

.. _hrm-ug-004:

Viewing and Modifying Basic Information of a RocketMQ Instance
==============================================================

This section describes how to view the details, and modify the basic information of a RocketMQ instance on the console.

After creating a RocketMQ instance, you can modify some configurations of it as required, including the instance name, description, and security group.

Prerequisite
------------

A RocketMQ instance has been created.

Viewing Basic Information of a RocketMQ Instance
------------------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Search for a RocketMQ instance by specifying the filters. Current filters include the status, name, version, instance type, specification, used/available storage space, AZ, enterprise project, and tag. For RocketMQ instance statuses, see :ref:`Table 1 <hrm-ug-004__en-us_topic_0143117211_table5086721717534>`.

   .. _hrm-ug-004__en-us_topic_0143117211_table5086721717534:

   .. table:: **Table 1** RocketMQ instance status description

      +-----------------------------------+---------------------------------------------------------------+
      | Status                            | Description                                                   |
      +===================================+===============================================================+
      | Creating                          | The instance is being created.                                |
      +-----------------------------------+---------------------------------------------------------------+
      | Running                           | The instance is running properly.                             |
      |                                   |                                                               |
      |                                   | Only instances in the **Running** state can provide services. |
      +-----------------------------------+---------------------------------------------------------------+
      | Faulty                            | The instance is not running properly.                         |
      +-----------------------------------+---------------------------------------------------------------+
      | Changing                          | The public access configurations are being modified.          |
      +-----------------------------------+---------------------------------------------------------------+
      | Change failed                     | The public access configurations failed to be modified.       |
      +-----------------------------------+---------------------------------------------------------------+

#. Click a RocketMQ instance name to go to the instance details page.

Modifying Basic Information of a RocketMQ Instance
--------------------------------------------------

#. Log in to the console.

#. Click |image3| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image4| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance name to go to the instance details page.

#. Modify parameters.

   .. table:: **Table 2** Connection information

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                 |
      +===================================+=============================================================================================================================================================================+
      | Instance Name                     | To modify the instance name, click |image5|.                                                                                                                                |
      |                                   |                                                                                                                                                                             |
      |                                   | You can customize a name that complies with the rules: 4-64 characters; starts with a letter; can contain only letters, digits, hyphens (-), and underscores (_).           |
      |                                   |                                                                                                                                                                             |
      |                                   | Services are not affected.                                                                                                                                                  |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Enterprise Project                | To modify the enterprise project, click |image6|.                                                                                                                           |
      |                                   |                                                                                                                                                                             |
      |                                   | Services are not affected.                                                                                                                                                  |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | To modify the description, click |image7|.                                                                                                                                  |
      |                                   |                                                                                                                                                                             |
      |                                   | Services are not affected.                                                                                                                                                  |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Public Access                     | Click |image8| to enable or disable public access. For details, see :ref:`Configuring Public Access for a RocketMQ Instance <hrm-ug-033>`.                                  |
      |                                   |                                                                                                                                                                             |
      |                                   | Disable the public access setting of a connected RocketMQ instance interrupts the connection. As a result, messages fail to be produced and consumed.                       |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Instance Address (Public Network) | This parameter is displayed only when public access is enabled.                                                                                                             |
      |                                   |                                                                                                                                                                             |
      |                                   | Address for connecting to the instance when public access is enabled.                                                                                                       |
      |                                   |                                                                                                                                                                             |
      |                                   | Modify the public connection address of a connected RocketMQ instance interrupts the connection. As a result, messages fail to be produced and consumed.                    |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | SSL                               | Access mode of the instance, can be changed as required. For details, see :ref:`Configuring SSL of a RocketMQ Instance <hrm-ug-061>`.                                       |
      |                                   |                                                                                                                                                                             |
      |                                   | Options:                                                                                                                                                                    |
      |                                   |                                                                                                                                                                             |
      |                                   | -  SSL: Ciphertext access with high security, but lower performance.                                                                                                        |
      |                                   | -  PLAINTEXT: Plaintext access with high performance, but lower security.                                                                                                   |
      |                                   | -  PERMISSIVE: Both ciphertext and plaintext access, depending on the client.                                                                                               |
      |                                   |                                                                                                                                                                             |
      |                                   | Modifying the access mode may have impact. For more information, see :ref:`Table 1 <hrm-ug-061__table5701125211560>`.                                                       |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ACL                               | ACL status of the instance. Click |image9| to enable ACL. For details, see :ref:`Enabling RocketMQ ACL <hrm-ug-070>`.                                                       |
      |                                   |                                                                                                                                                                             |
      |                                   | When ACL is enabled, message production and consumption require authentication.                                                                                             |
      |                                   |                                                                                                                                                                             |
      |                                   | Enabling ACL of a connected RocketMQ instance causes message production and consumption failures.                                                                           |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Message Retention                 | Click |image10| to modify message retention. For details, see :ref:`Changing RocketMQ Message Retention Period <hrm-ug-059>`.                                               |
      |                                   |                                                                                                                                                                             |
      |                                   | Modifying message retention does not restart the instance. But messages whose retention expires will be deleted and cannot be consumed.                                     |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Security Group                    | To modify the security group, click |image11|.                                                                                                                              |
      |                                   |                                                                                                                                                                             |
      |                                   | Modifying the security group to exclude the IP address of the RocketMQ instance will interrupt the connected instance, causing message production and consumption failures. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   After the parameters are modified, view the result in the following ways:

   -  After you change **Instance Name**, **Description**, **Public Access**, **ACL**, **Message Retention**, **Enterprise Project**, and **Security Group**, the result is displayed in the upper right corner.
   -  If **SSL** has been modified, go to the **Background Tasks** page to view the task progress and result.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0143929918.png
.. |image4| image:: /_static/images/en-us_image_0000001143589128.png
.. |image5| image:: /_static/images/en-us_image_0000002269988492.png
.. |image6| image:: /_static/images/en-us_image_0000002270091588.png
.. |image7| image:: /_static/images/en-us_image_0000002304701425.png
.. |image8| image:: /_static/images/en-us_image_0000002268909630.png
.. |image9| image:: /_static/images/en-us_image_0000002303542617.png
.. |image10| image:: /_static/images/en-us_image_0000002270337294.png
.. |image11| image:: /_static/images/en-us_image_0000002304834017.png
