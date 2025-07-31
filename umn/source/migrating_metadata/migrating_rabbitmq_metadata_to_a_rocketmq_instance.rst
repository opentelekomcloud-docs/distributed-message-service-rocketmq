:original_name: hrm-ug-056.html

.. _hrm-ug-056:

Migrating RabbitMQ Metadata to a RocketMQ Instance
==================================================

On the console, you can migrate RabbitMQ metadata to your DMS RocketMQ instance.

Prerequisites
-------------

-  A RocketMQ instance has been created.
-  `RabbitMQ plug-ins <https://www.rabbitmq.com/docs/management>`__ have been enabled.
-  A RabbitMQ 3.7.17/3.8.35 instance has been purchased.

.. _hrm-ug-056__section715034218237:

Step 1: Obtain RabbitMQ Metadata
--------------------------------

#. Enter **http://**\ *IP address of your RabbitMQ*\ **:15672/** in the address box of the browser to access the open-source RabbitMQ console.

#. On the login page, enter the username and password, and click **Login**.

   The default username and password are the ones configured in RabbitMQ instance creation.

#. On the **Overview** tab page, click **Download broker definitions** to export the metadata.


   .. figure:: /_static/images/en-us_image_0000001542962724.png
      :alt: **Figure 1** Exporting metadata

      **Figure 1** Exporting metadata

Step 2: Migrate Metadata on the Console
---------------------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the details page.

#. In the navigation pane, choose **Metadata Migration**.

#. Click **Create Migration Task**.

#. Configure the migration task by referring to :ref:`Table 1 <hrm-ug-056__table1791434413216>`.

   .. _hrm-ug-056__table1791434413216:

   .. table:: **Table 1** Migration task parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                     |
      +===================================+=================================================================================================================================================================================================================================+
      | Task Type                         | Select **From RabbitMQ to RocketMQ**.                                                                                                                                                                                           |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Task Name                         | Unique name of the migration task.                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   | A task name must meet the following requirements:                                                                                                                                                                               |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   | -  Contains 4 to 64 characters.                                                                                                                                                                                                 |
      |                                   | -  Contains only letters, digits, hyphens (-), and underscores (_), and must start with a letter.                                                                                                                               |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Overwrite                         | -  If this option is enabled, configurations in the metadata file with the same name as the uploaded file will be modified.                                                                                                     |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   |    Assume that Topic01 on the source instance has three read queues, and Topic01 on the DMS instance has two read queues. If **Overwrite** is enabled, Topic01 on the DMS instance will have three read queues after migration. |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   | -  If this option is disabled, migration of the metadata file with the same name as the uploaded file will fail.                                                                                                                |
      |                                   |                                                                                                                                                                                                                                 |
      |                                   |    Assume that the source instance has Topic01 and Topic02, and the DMS instance has Topic01 and Topic03. If **Overwrite** is disabled, migration of the source Topic01 will fail.                                              |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Metadata                          | Upload the :ref:`RabbitMQ metadata <hrm-ug-056__section715034218237>`.                                                                                                                                                          |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   After the migration is complete, view **Task Status** in the migration task list.

   -  If **Task Status** is **Complete**, all metadata has been successfully migrated.

   -  If **Task Status** is **Failed**, some or all metadata fails to be migrated.

      Click the migration task name to go to the migration task details page. In the **Migration Result** area, view the name of the topic or consumer group that fails to be migrated, the failure cause, and the solution.

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
