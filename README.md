# Ansible Role: Elasticsearch

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-elasticsearch.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-elasticsearch)

An Ansible Role that installs Elasticsearch on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Role Variables
Available variables are listed below, along with default values (see
`defaults/main.yml`):

    elasticsearch_network_host: localhost

Network host to listen for incoming connections on. By default we only listen
on the localhost interface. Change this to the IP address to listen on a
specific interface, or `0.0.0.0` to listen on all interfaces.

    elasticsearch_http_port: 9200

The port to listen for HTTP connections on.

    elasticsearch_script_inline: true
    elasticsearch_script_indexed: true

Whether to allow inline scripting against ElasticSearch. You should read the
following link as there are possible security implications for enabling these
options: [Enable Dynamic
Scripting](https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-scripting.html#enable-dynamic-scripting).
Available options are: `true`, `false`, `sandbox`.

## Dependencies

  - geerlingguy.java

## Example Playbook

    - hosts: search
      roles:
        - { role: geerlingguy.java }
        - { role: geerlingguy.elasticsearch }

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/),
author of [Ansible for DevOps](http://ansiblefordevops.com/).
