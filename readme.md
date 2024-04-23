### How many data your publlsher program will send to the message broker in one run?
In a single execution, the publisher program will transmit five messages to the message broker. This behavior can be discerned from the provided main() function, wherein the publisher program publishes five instances of the UserCreatedEventMessage to the message broker. Each invocation of the publish_event() method dispatches one message to the "user_created" queue.

### The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
The presence of the url "amqp://guest:guest@localhost:5672" in both the subscriber and publisher programs signifies that they are configured to connect to the same instance of the message broker. This configuration ensures that messages published by the publisher are routed to the appropriate message queue, enabling the subscriber to consume them. It establishes a communication channel between the two components of the system, facilitating a seamless exchange of messages.

## Screenshots

<img width="1470" alt="Screenshot 2024-04-23 at 21 56 06" src="https://github.com/PeakFiction/Tutorial8Publisher/assets/112671939/30557a9f-fbd7-4b1c-b9bb-47b0807f5cbe">

<img width="1258" alt="Screenshot 2024-04-23 at 22 02 43" src="https://github.com/PeakFiction/Tutorial8Publisher/assets/112671939/25f60b5d-857b-4a6b-b11a-f405d70d23d1">
Upon executing both the subscriber and publisher code, they establish a connection to the same AMQP message broker using the URL "amqp://guest:guest@localhost:5672". The publisher component transmits messages to the message broker, while the subscriber component receives and processes those messages, thereby demonstrating a basic publish-subscribe interaction facilitated by AMQP. The subscriber program listens for messages on the "user_created" queue and outputs each successfully received message, with a total of 5 messages being successfully acquired. Conversely, the publisher program publishes several instances of the UserCreatedEventMessage to the "user_created" queue. Each instance represents a user creation event, characterized by a unique user ID and name.

<img width="1470" alt="Screenshot 2024-04-23 at 22 05 33" src="https://github.com/PeakFiction/Tutorial8Publisher/assets/112671939/e12e0fb5-c252-4633-baa7-e4e250ca296c">

The chart in the following image illustrates the activity of the publisher in transmitting its message to the subscriber. The spikes observed in the second chart provide insights into the intensity of the load that the publisher sends, whether light or heavy, by depicting the message rates. This visual representation aids in comprehending the number of messages sent and processed within a given time frame. Moreover, the spikes on the chart also represent Consumer acks (colored purple), indicating the rate at which the messages from the publisher are being acknowledged by consumers (the subscriber).
