# Spotto MQTT Broker

## Introduction


Welcome to the Spotto MQTT Service

MQTT is a lightweight publish / subscribe messaging protocol that is popular among the IOT space. Whenever something significant happens in Spotto, like an asset moving or a reader coming online, Spotto will publish this information to an MQTT broker. Your own applications can subscribe to this stream and use the information to to solve bespoke business problems. 


## What is MQTT

MQTT uses a publish subscribe protocol where messages are communicated via topics.

The system consists of clients and an MQTT broker. Clients are able to publish messages to a topic, the broker then exposes that message to any clients who are subscribed to that topic.

## MQTT Topics
MQTT topics are hierarchical with levels of the hierarchy being separated by a /. 

E.g. your_organisation/Arrived/thingId1

Special wildcard character # can be used to subscribe to all topics at a level of the hierarchy. 

to subscribe to all arrived events for your organisation
your_organisation/Arrived/#

For more information on mqtt [click here](https://mqtt.org/getting-started/)

## Connecting to the broker
```javascript
import mqtt from 'async-mqtt';

const username = 'your_username';
const password = 'your_password';
const endpoint = 'mqtt://<spotto-mqtt-endpoint>';

const connect = () => {
	const connection = await mqtt.connectAsync(
		endpoint,
		{
			username,
			password,
		},
	);

	return connection;
};

```

## Subscribing to a topic
```javascript
// Use code snippet from previous section
const client = connect();

const topic = 'your_organisation/Arrived/thing_id';

client.subscribe(topic);

client.on('message', (topic, message) => {
  // message is Buffer
  console.log(message.toString())

	// Run your bespoke logic here
});

```

## Spotto Events

Spotto exposes the following Events as they occur.

### Arrived

Topic
<aside class="notice">
${organisation}/Arrived/${asset.id}
</aside>

```json
{
	"timestamp": "number",
	"organisation": "string",
	"type": "Arrived",
	"asset": {
		"id": "string",
		"name": "string", 
	},
	"location": {
		"id": "string",
		"name": "string", 
	},
	"reader": {
		"id": "string",
		"name": "string", 
	}
}

```