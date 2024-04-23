# Reflection for Publisher

- How many data your publlsher program will send to the message broker in one run? 

The publisher program will send five messages to the message broker in one run. This is because in the provided main() function, we can observe that the publisher program publishes five UserCreatedEventMessage instances to the message broker. Each publish_event() call sends one message to the "user_created" queue.:

```rust
_ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "1".to_owned(), user_name: "2206822963-Amir".to_owned() });
_ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "2".to_owned(), user_name: "2206822963-Budi".to_owned() });
_ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "3".to_owned(), user_name: "2206822963-Cica".to_owned() });
_ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "4".to_owned(), user_name: "2206822963-Dira".to_owned() });
_ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "5".to_owned(), user_name: "2206822963-Emir".to_owned() });
```

- The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean? 

Since the url of “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, this means that the subscriber and publisher are configured to connect to the same message broker instance. This ensures that messages published by the publisher are sent to the correct message queue and can be consumed by the subscriber. It establishes a communication channel between the two components of the system, allowing them to exchange messages seamlessly.

-------------------------------------------------------------------------------------------------------------
# Screenshots

## Running RabbitMQ

![Screenshot 2024-04-23 083506.png](assets%2FScreenshot%202024-04-23%20083506.png)