# Real time data visualisation test

At Quro, one very critical aspect of the work is to ensure that Medical Practitioners have patient data in real time, and accurately. We need you to get to work, right away. Develop a reactjs app to display live client ecg data for a medical practitioner.

Your task is to write a simple react client to visualise ecg data published to an mqtt topic in real time.

You will be given A simple nodejs server app that publishes real ecg data to an mqtt channel.

This repo contains an **ecg-server**, an **Express.js - MQTT - Socket.io** application, which will work in conjunction with a reactjs client you are to build.

## Components of the system

### Server
+ publishes and subscribes to MQTT topic (i.e. **ecg**)
+ forwards the received messages to the client using websockets

### Mqtt broker
+ can be any mqtt broker of your choosing

### Client (to be built by you)
+ real-time data visualization with a time-eries line chart

## Getting Started

### Prerequisites

Before you run the client, be sure you have these downloaded/installed on your machine:

+ node.js
+ npm
+ [Moquette (MQTT broker)](https://github.com/andsel/moquette) (or any other MQTT broker that listens on port 1883)
    + If using Moquette, be sure to have Java JDK installed (tested with JDK 8)

### Installing

To get started with this project, follow the 3-step installation, described here.

## 1. Moquette 

The following commands will unpack and run the Moquette broker, which listens on port 1883:

```
tar zxf distribution-0.10-bundle-tar.tar.gz
cd bin
./moquette.sh	
```

*Windows specific:*

```
cd bin
.\moquette.bat 
```


## 2. ecg-server  (this repo)

Navigate inside the root folder and run:

```
npm install
npm start
```
this will install the dependencies and start the express server locally on port 3000.

If the server-app and Moquette are already running in separate terminals, you can see the data stream inside the terminal. You can also check out the stream with a 3rd party MQTT client (e.g. MQTTfx) by connecting to **0.0.0.0:1883** and subscribing to topic **ecg**.

Each data publish will be in the form of an array of objects with two properties: timestamp (the time the reading was taken) and ecg (the ecg value reading recorded at the time of the timestamp)


## 3. mqtt-realtime-client (your app)

*Before start working on the client, it's advised that you would have already completed steps 1 and 2, and have both Moquette and the ecg-server running in separate terminal windows.*

The client is required to perform the following tasks:
+ Subscribe to realtime data updates from the server by connecting to **0.0.0.0:1883** and subscribing to mqtt topic **ecg**
+ Visualise the ecg data in real time.


## Built With


### Server
* [Express.js](https://github.com/expressjs/express) - minimalist web framework for node.
* [Socket.io](https://github.com/socketio/socket.io) - real-time bidirectional event-based communication using websockets
* [MQTT.js](https://github.com/mqttjs/MQTT.js) - MQTT client for Node.js and the browser

"# plotly_real_time_updates" 
