:original_name: hrm-ug-028.html

.. _hrm-ug-028:

Enabling and Querying RocketMQ Message Tracing
==============================================

Message traces contain complete time and location information during production and consumption of a message. Message tracing enables diagnosis of real messaging status when exceptions (e.g., production and consumption failures) occur. Message traces can be queried by message ID, message key, or topic time range.

The following procedures describe how to enable and query message tracing in Java, Go, and Spring.

Prerequisites
-------------

-  Transactional message tracing is supported only if the producer Java client is v4.9.0 or later. If your client is earlier than v4.9.0, upgrade it to a later version.
-  For RocketMQ instances with SSL enabled, message tracing is supported only when the producer and consumer Java clients are v4.9.2 or later. If the version does not meet the requirement, upgrade it first.

Enabling RocketMQ Message Tracing (Java)
----------------------------------------

Do as follows to enable message tracing on clients:

-  Enabling message tracing on a producer client (**tracing messages other than transactional messages**)

   Set **enableMsgTrace** of the constructor to **true**. For example:

   .. code-block::

      DefaultMQProducer producer = new DefaultMQProducer("ProducerGroupName", true);

-  Enabling message tracing on a producer client (**tracing transactional messages**)

   Set **enableMsgTrace** of the constructor to **true**. For example:

   .. code-block::

      TransactionMQProducer producer = new TransactionMQProducer(null, "ProducerGroupName", null, true, null);

-  Enabling message tracing on a consumer

   Set **enableMsgTrace** of the constructor to **true**. For example:

   .. code-block::

      DefaultMQPushConsumer consumer = new DefaultMQPushConsumer("ConsumerGroupName", true);

Enabling RocketMQ Message Tracing (Go)
--------------------------------------

Do as follows to enable message tracing on clients:

#. Run the following command to check whether Go has been installed:

   .. code-block::

      go version

   If the following information is displayed, Go has been installed.

   .. code-block:: console

      [root@ecs-test sarama]# go version
      go version go1.16.5 linux/amd64

   If Go is not installed, `download <https://go.dev/dl/go1.16.5.linux-amd64.tar.gz>`__ and install it.

#. Go to the **bin** directory where the **Go** script is in.

#. Run the **touch go.mod** command to create a **go.mod** file and add the following code to it to add the dependency:

   .. code-block::

      module rocketmq-example-go

      go 1.13

      require (
          github.com/apache/rocketmq-client-go/v2 v2.1.0
      )

#. Enable message tracing on the producer. Replace the information in bold with the actual values.

   .. code-block::

      package main

      import (
          "context"
          "fmt"
          "os"
          "time"

          "github.com/apache/rocketmq-client-go/v2"
          "github.com/apache/rocketmq-client-go/v2/primitive"
          "github.com/apache/rocketmq-client-go/v2/producer"
      )

      func main() {
          namesrvs := []string{"192.168.0.1:8100"}
          traceCfg := &primitive.TraceConfig{
              Access:   primitive.Local,
              Resolver: primitive.NewPassthroughResolver(namesrvs),
          }

          p, _ := rocketmq.NewProducer(
              producer.WithNsResolver(primitive.NewPassthroughResolver([]string{"192.168.0.1:8100"})),
              producer.WithRetry(2),
              producer.WithTrace(traceCfg))   // To enable message tracing, add this line.
          err := p.Start()
          if err != nil {
              fmt.Printf("start producer error: %s", err.Error())
              os.Exit(1)
          }
          res, err := p.SendSync(context.Background(), primitive.NewMessage("topic1",
              []byte("Hello RocketMQ Go Client!")))

          if err != nil {
              fmt.Printf("send message error: %s\n", err)
          } else {
              fmt.Printf("send message success: result=%s\n", res.String())
          }

          time.Sleep(10 * time.Second)

          err = p.Shutdown()
          if err != nil {
              fmt.Printf("shutdown producer error: %s", err.Error())
          }
      }

#. Enable message tracing on the consumer. Replace the information in bold with the actual values.

   .. code-block::

      package main

      import (
          "context"
          "fmt"
          "os"
          "time"

          "github.com/apache/rocketmq-client-go/v2"
          "github.com/apache/rocketmq-client-go/v2/consumer"
          "github.com/apache/rocketmq-client-go/v2/primitive"
      )

      func main() {
          namesrvs := []string{"192.168.0.1:8100"}
          traceCfg := &primitive.TraceConfig{
              Access:   primitive.Local,
              Resolver: primitive.NewPassthroughResolver(namesrvs),
          }

          c, _ := rocketmq.NewPushConsumer(
              consumer.WithGroupName("testGroup"),
              consumer.WithNsResolver(primitive.NewPassthroughResolver([]string{"192.168.0.1:8100"})),
              consumer.WithTrace(traceCfg),   // To enable message tracing, add this line.
          )
          err := c.Subscribe("TopicTest", consumer.MessageSelector{}, func(ctx context.Context,
              msgs ...*primitive.MessageExt) (consumer.ConsumeResult, error) {
              fmt.Printf("subscribe callback: %v \n", msgs)
              return consumer.ConsumeSuccess, nil
          })
          if err != nil {
              fmt.Println(err.Error())
          }
          // Note: start after subscribe
          err = c.Start()
          if err != nil {
              fmt.Println(err.Error())
              os.Exit(-1)

          }
          time.Sleep(time.Hour)
          err = c.Shutdown()
          if err != nil {
              fmt.Printf("shutdown Consumer error: %s", err.Error())
          }
      }

Enabling RocketMQ Message Tracing (Spring)
------------------------------------------

Do as follows to enable message tracing on clients:

-  For producers

   Add the following line in the **application.properties** configuration file:

   .. code-block::

      rocketmq.producer.enable-msg-trace=true

-  For consumers

   Set parameter **enableMsgTrace** to **true**. For example:

   .. code-block::

      @Service
      @RocketMQMessageListener(
          topic = "test-topic-1",
          consumerGroup = "my-consumer_test-topic-1",
          enableMsgTrace = true
      )
      public class MyConsumer implements RocketMQListener<String> {
          ...
      }

   Replace the information in bold with the actual values.

For details, see `Message Tracing <https://github.com/apache/rocketmq-spring/wiki/Message-Tracing>`__.

.. caution::

   The default value of parameter **accessChannel** is **LOACL**. Use the default value.

Viewing the Message Trace
-------------------------

#. Log in to the console.

#. Click |image1| in the upper left corner to select a region.

   DMS for RocketMQ instances in different regions cannot communicate with each other over an intranet. Select a nearest location for low latency and fast access.

#. Click |image2| and choose **Application** > **Distributed Message Service for RocketMQ** to open the console of DMS for RocketMQ.

#. Click a RocketMQ instance to go to the instance details page.

#. In the navigation pane, choose **Message Query**.

#. Query messages in either of the following ways:

   -  By topic: Select the topic to be queried from the **Topic** drop-down list and the queue to the queried from the **Queue** drop-down list (only for RocketMQ 4.8.0). For **Stored**, select a time period.
   -  By message ID: Select the name of the topic to be queried from the **Topic** drop-down list, enter the ID of the message to be queried, and click **Search**.
   -  By message key: Select the name of the topic to be queried from the **Topic** drop-down list, enter the key of the message to be queried, and click **Search**.

#. Locate the row containing the message to be queried. Click **Message Trace**.

#. View the message trace to check whether the message is successfully produced or consumed.

   :ref:`Table 1 <hrm-ug-028__table8707194615415>` describes message trace parameters.

   .. _hrm-ug-028__table8707194615415:

   .. table:: **Table 1** Message trace parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                   |
      +===================================+===============================================================================================================================================+
      | Producer status                   | A producer can be in one of the following states:                                                                                             |
      |                                   |                                                                                                                                               |
      |                                   | -  **Sent**: The message is sent successfully, and the server has successfully stored the message.                                            |
      |                                   | -  **Committed**: The message can be retrieved by consumers.                                                                                  |
      |                                   | -  **Rollback**: The message will be discarded and cannot be retrieved by consumers.                                                          |
      |                                   | -  **Unknown**: The status of the message cannot be determined. After a period of time, the server initiates a check request to the producer. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
      | Creation duration                 | Time taken to send the message by the producer.                                                                                               |
      |                                   |                                                                                                                                               |
      |                                   | Unit: millisecond                                                                                                                             |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
      | Producer address                  | IP address of the producer.                                                                                                                   |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
      | Consumer status                   | A consumer can be in one of the following states:                                                                                             |
      |                                   |                                                                                                                                               |
      |                                   | -  Retrieved                                                                                                                                  |
      |                                   | -  Retrieval timed out                                                                                                                        |
      |                                   | -  Abnormal retrieval                                                                                                                         |
      |                                   | -  NULL returned                                                                                                                              |
      |                                   | -  Retrieval failed                                                                                                                           |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
      | Retrieved                         | Time when the message is retrieved.                                                                                                           |
      |                                   |                                                                                                                                               |
      |                                   | The time format is *YYYY/MM/DD hh:mm:ss*.                                                                                                     |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
      | Retrieval duration                | Time taken to retrieve the message by the consumer.                                                                                           |
      |                                   |                                                                                                                                               |
      |                                   | Unit: millisecond                                                                                                                             |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
      | Consumer address                  | IP address of the consumer.                                                                                                                   |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0143929918.png
.. |image2| image:: /_static/images/en-us_image_0000001143589128.png
