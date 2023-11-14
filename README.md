# elastic_iot_poc
A simple Docker compose that starts an all-in-one environment to simulate IoT data sent to the Elastichsearch instance.
The example esecute the following components:
* Elasticsearch (https://www.elastic.co/guide/en/elasticsearch/reference/8.7/index.html)
* Kibana (https://www.elastic.co/guide/en/kibana/8.7/index.html)
* Mosquitto MQTT Broker
* An IoT Simulator (https://github.com/massimocallisto/iot-simulator)
* A filebeat to send IoT events to Elasticsearch (https://www.elastic.co/guide/en/beats/filebeat/8.7/filebeat-overview.html)
* A filebeat with a javascript processor login to handle the message event before sending to  Elasticsearch that is, perform a flattering of a nested JSON (https://www.elastic.co/guide/en/beats/filebeat/8.7/processor-script.html)


## Requirements
You need a running Doker and Docker compose instances in your system.
Linux works fine in general.

## Execute the environment
Clone the repo, move within the main folder and launch the docker compose with the following command:

    docker-compose up

Note for ARM platforms (e.g. Mac Mx processor). You need to run a different docker compose file:

    docker-compose up -f docker-compose-arv64v8.yml

## Visualize the data
Connect to Kibana to `http://YOUR_IP:5601`, configure the index and check the data.

