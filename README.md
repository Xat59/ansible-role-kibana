# Ansible Role: Kibana

<p align="center">
    <a id="kibana" href="#kibana">
        <img src="https://github.com/Xat59/ansible-role-kibana/blob/master/media/kibana.png" alt="Kibana title" title="Kibana title" width="600"/>
    </a>
</p>

<p align="center">
[![Build Status](https://travis-ci.org/Xat59/ansible-role-kibana.svg?branch=master)](https://travis-ci.org/Xat59/ansible-role-kibana)
</p>

An Ansible Role that installs Kibana on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Role Variables

All Kibana configuration parameters are supported. This is achieved using a configuration map parameter `kibana_conf` which is serialized into the ${kibana}.yml file. The use of a map ensures the Ansible playbook does not need to be updated to reflect new/deprecated/plugin configuration parameters.

    kibana_conf: ""

In addition to the kibana_conf map, several other parameters are supported for basic functions. These can be found below.

    kibana_version: "7.x"

The version of kibana to install.

    kibana_package: kibana
    kibana_package_state: present

The specific package to be installed. You can specify a version of the package using the correct syntax for your platform and package manager by changing the package name. You can also control the package state (e.g. `present`, `absent`, or `latest`).

    kibana_service_state: started
    kibana_service_enabled: true

Controls whether the `kibana` service is started and enabled on system boot.

    kibana_config_template: kibana.yml.j2
    kibana_config_file_path: /etc/kibana/kibana.yml

The template to use for the Kibana config file, and the path to which the config file will be written.

    kibana_server_port: 5601
    kibana_server_host: "0.0.0.0"

The FQDN or IP address and port Kibana should use.

    kibana_elasticsearch_url: "http://localhost:9200"

The URL (including port) over which Kibana will connect to Elasticsearch.

    kibana_elasticsearch_username: ""
    kibana_elasticsearch_password: ""

If Elasticsearch is protected by HTTP basic authentication, set the username and password so Kibana can connect.

## Dependencies

None.

## Example Playbook

    - hosts: kibana
      roles:
        - Xat59.kibana

## License

MIT / BSD

## Author Information

This role was forked by Xat59 in 2020 from a good work of Jeff Geerling.
