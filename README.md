# Docker ELK stack

Run the ELK (Elasticseach, Logstash, Kibana) stack with Docker and Docker-compose.

It will give you the ability to quickly test your logstash filters and check how the data can be processed in Kibana.

## Setup

1. Install [Docker](http://docker.io).
2. Install [docker-compose](http://docs.docker.com/compose/install/).
3. Clone this repository

## Usage

### Start the stack and inject logs

First step, you can edit the logstash-configuration in *config/logstash.conf*. You can add filters you want to test for example.

Then, start the ELK stack using *docker-compose*:

```
$ docker-compose up
```

You can also choose to run it in background (detached mode):

```
$ docker-compose up -d
```

Now that the stack is running, you'll want to inject logs in it. The shipped logstash configuration allows you to send content via tcp:

```
$ nc localhost 3333 < /path/to/logfile.log
```
## Credits

[willdurand/docker-elk](https://github.com/willdurand/docker-elk)
