### How many data your publlsher program will send to the message broker in one run?
In a single execution, the publisher program will transmit five messages to the message broker. This behavior can be discerned from the provided main() function, wherein the publisher program publishes five instances of the UserCreatedEventMessage to the message broker. Each invocation of the publish_event() method dispatches one message to the "user_created" queue.

### The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
The presence of the url "amqp://guest:guest@localhost:5672" in both the subscriber and publisher programs signifies that they are configured to connect to the same instance of the message broker. This configuration ensures that messages published by the publisher are routed to the appropriate message queue, enabling the subscriber to consume them. It establishes a communication channel between the two components of the system, facilitating a seamless exchange of messages.

## Screenshots