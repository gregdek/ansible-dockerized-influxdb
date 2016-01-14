InfluxDB (Dockerized)
=====================

Sample Galaxy role, forked from blixtra, to show an example of how Ansible+Atomic might work together with a properly Dockerized role.

Simple ansible role for dockerized InfluxDB. Used to set up a single instance of InfluxDB or a cluster using the SEEDS environment variable.

Variables
=========

```
admin_port: 8083
http_port: 8086
https_port: 8084
raft_port: 8090
protobuf_port: 8099
docker_api_version: 1.15
```

Install
=======

1. git clone this repo (in future, ansible-galaxy install this.galaxy.role)
2. vagrant up
3. in your browser, goto localhost:8083
4. ??? (lol)
