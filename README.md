# Elastc stack (ELK) on Docker

This is a docker-compose stack for the Elastic stack (ELK). It is based on the official docker images from elastic.co.
The stack inject data from the Logstash folder into elasticsearch and visualize it in kibana.
Additionally it contains a Filebeat container to inject data from the host system into logstash.

Two directories:
./filebeat_ingest_data
./logstash_ingest_data

Can be used initially to inject data into the stack.

## Usage

Adding .env file with the following variables:

```# Password for the 'elastic' user (at least 6 characters)
ELASTIC_PASSWORD=

# Password for the 'kibana_system' user (at least 6 characters)
KIBANA_PASSWORD=

# Version of Elastic products
STACK_VERSION=8.11.0

# Set the cluster name
CLUSTER_NAME=clustername

# Set to 'basic' or 'trial' to automatically start the 30-day trial
LICENSE=basic
#LICENSE=trial

# Port to expose Elasticsearch HTTP API to the host
ES_PORT=9200
#ES_PORT=127.0.0.1:9200

# Port to expose Kibana to the host
KIBANA_PORT=5601
#KIBANA_PORT=80

# Increase or decrease based on the available host memory (in bytes)
MEM_LIMIT=1073741824

# Project namespace (defaults to the current folder name if not set)
COMPOSE_PROJECT_NAME=elk-stack

# SAMPLE Predefined Key only to be used in POC environments
ENCRYPTION_KEY=c34d38b3a14956121fa2170e503aa471351374178f43e5626eec58b04a30fae2
```

To start the stack, simply run `docker-compose up -d`. 