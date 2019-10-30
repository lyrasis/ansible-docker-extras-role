Ansible Role: Docker Extras
=========

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Performs configuration and extra tasks to support Docker


Requirements
------------

Some means of installing Docker. We currently use https://galaxy.ansible.com/angstwad/docker_ubuntu


Role Variables
--------------

    # instances is an array of dicts that have at least a name key
    # example: docker_instances: [ { name: "nginx" } ]
    docker_instances: []

    # the base path used for docker instances i.e. /root/nginx
    docker_base_path: "/root"

    # instance suffix is a name used to identify a docker compose template
    # of the form: templates/compose-{{ docker_compose_suffix }}.yml.j2
    # these should be defined at the root level of the playbook
    # example: docker_compose_suffix: nginx
    docker_compose_suffix: ""

    # docker log file
    docker_log: /var/log/docker.log

    # logrotate size in MB for docker log
    docker_log_size: 512

    # logrotate days for docker log
    docker_log_rotate: 2

Dependencies
------------

None (see Requirements)


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: docker-extras }


License
-------

The project is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
