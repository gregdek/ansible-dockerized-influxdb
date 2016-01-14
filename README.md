Docker InfluxDB
===============

Sample Galaxy role, forked from blixtra, to show an example of how Ansible+Atomic might work together.

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

Dependencies
============

Requires Ansible 1.8 as it uses new Docker module functionality.

Needs Docker to be running on remote system.
