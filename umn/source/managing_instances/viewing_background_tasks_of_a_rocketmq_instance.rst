:original_name: hrm-ug-062.html

.. _hrm-ug-062:

Viewing Background Tasks of a RocketMQ Instance
===============================================

After you initiate certain instance operations listed in :ref:`Table 1 <hrm-ug-062__table135711125812>`, a background task will start for each operation. On the console, you can view the background task status and clear task information by deleting task records.

.. _hrm-ug-062__table135711125812:

.. table:: **Table 1** Backend task list

   +-----------------------------------+----------------------------------------------+
   | Task Name                         | Description                                  |
   +===================================+==============================================+
   | Creating an Instance              | Creates a RocketMQ instance.                 |
   +-----------------------------------+----------------------------------------------+
   | Changing SSL setting              | Changes the SSL configuration.               |
   +-----------------------------------+----------------------------------------------+
   | Enable public access              | Enables **Public Access**.                   |
   +-----------------------------------+----------------------------------------------+
   | Disable public access             | Disable **Public Access**.                   |
   +-----------------------------------+----------------------------------------------+
   | Modify Specifications             | -  Expands the storage space.                |
   |                                   | -  Increases the instance flavor.            |
   +-----------------------------------+----------------------------------------------+
   | Deleting ConsumerGroup in Batches | Deletes multiple consumer groups in batches. |
   +-----------------------------------+----------------------------------------------+
   | Deleting Topics in Batches        | Deletes multiple topics in batches.          |
   +-----------------------------------+----------------------------------------------+
   | Restart Broker                    | Restarts brokers.                            |
   +-----------------------------------+----------------------------------------------+
   | Metadata Migration                | Migrates metadata.                           |
   +-----------------------------------+----------------------------------------------+

Prerequisite
------------

A RocketMQ instance has been created.

Procedure
---------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Instance** > **Background Tasks**.

#. On the **Current Tasks** or **Scheduled Tasks** tab page, specify a time range in the upper left corner. The task information in that time range will be displayed.

   On the **Background Tasks** page, you can also do as follows:

   -  Query specific RocketMQ instances by filtering. Current filters include the task name, username, status, and other information.

   -  Click |image3| to refresh the task status.

   -  Click **Delete**. In the displayed **Delete Task** dialog box, click **OK** to clear the task information.

      Select tasks and click **Delete** in the upper right corner to delete them in batches.

      The deletion is allowed when the task is in the **Successful** or **Failed** state.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
.. |image3| image:: /_static/images/en-us_image_0000002328408041.png
