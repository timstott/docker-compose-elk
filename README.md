# Docker ELK stack

Run the ELK (Elasticseach, Logstash, Kibana) stack with docker and docker-compose.

## Setup

Basics docker and docker-compose
1. Install [Docker](http://docker.io)
   Easily install Docker on OS X with [Kitematic](https://kitematic.com/).
2. Install [docker-compose](http://docs.docker.com/compose/install/).

Configure port forwarding (OS X only)
1. Open VirtualBox
2. select your docker machine (usualy dev)
3. Click *Settings*
4. Select *Network*
5. Click *Port forwarding*
6. Add the following 2 entries
   logstash, UDP, 127.0.0.1, 5005, ,5005
   logstash, TCP, 127.0.0.1, 5005, ,5005

Clone this repository
## Usage

Start the ELK stack using *docker-compose*:

```
$ docker-compose up
```

Send content via tcp

```
$ nc localhost 5005 < /example/log.json
```

Receive data from remote host with remote port forwarding:
```
ssh example.co.uk -R 5005:localhost:5005
```

The logstash configuration drops empty messages.
You can edit logstash configuration in *config/logstash.conf*.

## Credits

- [willdurand/docker-elk](https://github.com/willdurand/docker-elk)
