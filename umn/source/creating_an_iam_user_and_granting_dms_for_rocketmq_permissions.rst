:original_name: hrm-ug-030.html

.. _hrm-ug-030:

Creating an IAM User and Granting DMS for RocketMQ Permissions
==============================================================

This section describes how to use `Identity and Access Management (IAM) <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0026.html>`__ for fine-grained permissions control for your Distributed Message Service (DMS) for RocketMQ resources. With IAM, you can:

-  Create IAM users for personnel based on your enterprise's organizational structure. Each IAM user has their own identity credentials for accessing DMS for RocketMQ resources.
-  Grant users only the permissions required to perform a given task based on their job responsibilities.
-  Entrust an account or a cloud service to perform efficient O&M on your DMS for RocketMQ resources.

If your account meets your permissions requirements, you can skip this section.

This section describes the procedure for granting user permissions. :ref:`Figure 1 <hrm-ug-030__fig1100175132012>` shows the process flow.

Prerequisites
-------------

Learn about the permissions (see :ref:`Permissions Management <hrm-pd-011>`) supported by DMS for RocketMQ and choose policies or roles according to your requirements. For the system policies of other services, see `Permissions <https://docs.otc.t-systems.com/en-us/permissions/index.html>`__.

**DMS for RocketMQ permissions policies are based on DMS. Therefore, when assigning permissions, select DMS permissions policies.**

Process Flow
------------

.. _hrm-ug-030__fig1100175132012:

.. figure:: /_static/images/en-us_image_0000001239417092.png
   :alt: **Figure 1** Process for granting DMS for RocketMQ permissions

   **Figure 1** Process for granting DMS for RocketMQ permissions

#. On the IAM console, `create a user group and grant it permissions <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0030.html>`__.

   **DMS ReadOnlyAccess** is used as an example.

#. `Create an IAM user and add it to the created user group <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0031.html>`__.

#. `Log in as the IAM user <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0032.html>`__ and verify permissions.

   In the authorized region, perform the following operations:

   -  Choose **Service List** > **Distributed Message Service**. Then click **Create Instance** on the console of DMS for RocketMQ. If a message appears indicating that you have insufficient permissions to perform the operation, the **DMS ReadOnlyAccess** policy is in effect.
   -  Choose **Service List** > **Elastic Volume Service**. If a message appears indicating that you have insufficient permissions to access the service, the **DMS ReadOnlyAccess** policy is in effect.

Example Custom Policies
-----------------------

Custom policies can be created to supplement the system-defined policies of DMS for RocketMQ. For the actions that can be added for custom policies, see Permissions Policies and Supported Actions.

To create a custom policy, choose either visual editor or JSON.

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Create a JSON policy or edit an existing one.

For details, see `Creating a Custom Policy <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0016.html>`__. This section lists examples of common DMS for RocketMQ custom policies.

-  Example 1: Grant permission to delete and restart instances.

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "dms:instance:modifyStatus",
                      "dms:instance:delete"
                  ]
              }
          ]
      }

-  Example 2: Grant permission to deny instance deletion.

   A policy with only "Deny" permissions must be used together with other policies. If the permissions granted to an IAM user contain both "Allow" and "Deny", the "Deny" permissions take precedence over the "Allow" permissions.

   Assume that you want to grant the permissions of the **DMS FullAccess** policy to a user but want to prevent them from deleting instances. You can create a custom policy for denying instance deletion, and attach this policy together with the **DMS FullAccess** policy to the user. As an explicit deny in any policy overrides any allows, the user can perform all operations on instances excepting deleting them.

   Example policy denying instance deletion:

   .. code-block::

      {
              "Version": "1.1",
              "Statement": [
                      {
                              "Effect": "Deny",
                              "Action": [
                                      "dms:instance:delete"
                              ]
                      }
              ]
      }

DMS for RocketMQ Resources
--------------------------

A resource is an object that exists within a service. DMS for RocketMQ resources include **reliability**. To select these resources, specify their paths.

.. table:: **Table 1** DMS for RocketMQ resources and their paths

   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | Resource              | Resource Name         | Path                                                                                                                                              |
   +=======================+=======================+===================================================================================================================================================+
   | rocketmq              | Instance              | [Format]                                                                                                                                          |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | DMS:``*``:``*``: rocketmq:*instance ID*                                                                                                           |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | [Note]                                                                                                                                            |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | For instance resources, IAM automatically generates the prefix (**DMS:*:*:rocketmq:**) of the resource path.                                      |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | For the path of a specific instance, add the *instance ID* to the end. You can also use an asterisk **\*** to indicate any instance. For example: |
   |                       |                       |                                                                                                                                                   |
   |                       |                       | **DMS:*:*:rocketmq:\*** indicates any RocketMQ instance.                                                                                          |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+

DMS for RocketMQ Request Conditions
-----------------------------------

Request conditions are useful in determining when a custom policy is in effect. A request condition consists of condition keys and operators. Condition keys are either global or service-level and are used in the Condition element of a policy statement. `Global condition keys <https://docs.otc.t-systems.com/en-us/usermanual/iam/iam_01_0017.html>`__ (starting with **g:**) are available for operations of all services, while service-specific condition keys (starting with a service name such as **dms:**) are available only for operations of specific services. An operator must be used together with a condition key to form a complete condition statement.

DMS for RocketMQ has a group of predefined condition keys that can be used in IAM. For example, to define an "Allow" permission, use the condition key dms:ssl to filter instances by SSL configurations. The following table lists the DMS for RocketMQ predefined condition keys.

.. table:: **Table 2** Predefined condition keys of DMS for RocketMQ

   ============= ======== ================================
   Condition Key Operator Description
   ============= ======== ================================
   dms:publicIP  Bool     Whether public access is enabled
   dms:ssl       Bool     Whether SSL is enabled
   ============= ======== ================================
