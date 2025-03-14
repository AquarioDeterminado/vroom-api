# MQTT Application with Clients

## To test the code you need to

Run the docker-compose.yml
Run the mqtt_sub.py && mqtt-pub.py on separate terminals
Open MQTT Explorer and connect it to the broker (only needed the first time)
Then you can test the responses on the mqtt-pub.py terminal that sends the info to be received on both the MQTT Explorer && mqtt_sub.py

## Relevant links

MQTT Explorer - [https://mqtt-explorer.com/]

Node Red - [http://127.0.0.1:1880]

## Installed Widgets for Red Node

npm i node-red-node-ui-list

## To run the project run

Install mosquitto on [https://mosquitto.org/download/]
Install Red-Node on [https://nodered.org/docs/getting-started/local]
Install necessary Red-Node Widget on [https://flows.nodered.org/node/@flowfuse/node-red-dashboard]
run start_services.sh
run mqtt_sub.py && mqtt-pub.py

## Mongo Steps Taken

use admin

db.createUser({
    user: "admin",
    pwd: "password",  // Ensure this matches the password in the docker-compose file
    roles: [{ role: "root", db: "admin" }]
});

mongodb://admin:password@localhost:27017/?authSource=admin

db.createCollection("velocities")
db.createCollection("trips")
db.createCollection("trip_velocities")

### insert test item

db.velocities.insertOne({ time: new Date(), velocity: 60.5 })
db.trips.insertOne({ start_time: new Date("2025-03-11T08:00:00Z"), end_time: new Date("2025-03-11T10:00:00Z") })
