ansible-docker
==============

Installs Docker and configure it.

Requirements
------------

systemd-ready operating system.

Dependencies
------------

* [AerisCloud.repos](https://github.com/AerisCloud/ansible-repos)

Example Playbook
----------------

```yaml
- hosts: docker
  roles:
    - role: AerisCloud.docker
      docker_ip: "{{ ansible_eth0.ipv4.address }}"
      docker_log_driver: "journald"
      docker_insecure_registries: "{{ hostvars.myregistry.ansible_eth0.ipv4.address }}"
```

Role Variables
--------------

Those variables map directly to docker configuration entries, please see
the [dockerd documentation](https://docs.docker.com/engine/reference/commandline/dockerd/)
for more details about what each of these do.

| variable                   | type          |
|----------------------------|---------------|
| docker_hosts               | array(string) |
| docker_ip                  | string        |
| docker_ip                  | string        |
| docker_bip                 | string        |
| docker_fixed_cidr          | string        |
| docker_default_gateway     | string        |
| docker_dns                 | array(string) |
| docker_dns_opts            | array(string) |
| docker_dns_search          | array(string) |
| docker_log_driver          | string        |
| docker_log_level           | string        |
| docker_log_opts            | object        |
| docker_labels              | array(string) |
| docker_tls                 | object        |
| docker_tls.enabled         | bool          |
| docker_tls.verify          | bool          |
| docker_tls.cacert          | string        |
| docker_tls.cert            | string        |
| docker_tls.key             | string        |
| docker_registry_mirror     | array(string) |
| docker_insecure_registries | array(string) |

License
-------

Apache

Author Information
------------------

Christophe Robin <crobin@nekoo.com>