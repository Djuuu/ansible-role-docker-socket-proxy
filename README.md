Ansible Role: Docker-socket-proxy
=================================

Install docker-socket-proxy.

- https://github.com/Tecnativa/docker-socket-proxy
- https://github.com/linuxserver/docker-socket-proxy

Based on LinuxServer.io image: https://docs.linuxserver.io/images/docker-socket-proxy/

Requirements
------------

Requires the following to be installed:
- docker
- docker compose

Role Variables
--------------

Common Docker projects variables:

```yaml
# Base directory for Docker projects
docker_projects_path: # /var/apps
```

Available role variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# Docker project variables

docker_socket_proxy_project_name: docker-socket-proxy

# Docker socket proxy service additional docker-compose options (ex: cpu_shares, deploy, ...)
docker_socket_proxy_compose_service_additional_options: |
  #ports:
  #  - "2375:2375"


# Docker socket proxy project variables

# lscr.io/linuxserver/socket-proxy image version
docker_socket_proxy_version: latest

# Docker socket proxy network mode (bridge|host)
docker_socket_proxy_network_mode: bridge
```

Environment / access configuration.  
(See [_Grant or revoke access to certain API sections_](https://github.com/Tecnativa/docker-socket-proxy?tab=readme-ov-file#grant-or-revoke-access-to-certain-api-sections))

```yaml
# Docker socket proxy variables

docker_socket_proxy_env_allow_start:    0 # Not always needed
docker_socket_proxy_env_allow_stop:     0 # Not always needed
docker_socket_proxy_env_allow_restarts: 0 # Not always needed
docker_socket_proxy_env_auth:           0 # ⚠️ Security-critical
docker_socket_proxy_env_build:          0 # Not always needed
docker_socket_proxy_env_commit:         0 # Not always needed
docker_socket_proxy_env_configs:        0 # Not always needed
docker_socket_proxy_env_containers:     0 # Not always needed
docker_socket_proxy_env_disable_ipv6:   0
docker_socket_proxy_env_distribution:   0 # Not always needed
docker_socket_proxy_env_events:         1 # ✔️ Granted by default
docker_socket_proxy_env_exec:           0 # Not always needed
docker_socket_proxy_env_grpc:           0 # Not always needed
docker_socket_proxy_env_images:         0 # Not always needed
docker_socket_proxy_env_info:           0 # Not always needed
docker_socket_proxy_env_log_level:      info
docker_socket_proxy_env_networks:       0 # Not always needed
docker_socket_proxy_env_nodes:          0 # Not always needed
docker_socket_proxy_env_ping:           1 # ✔️ Granted by default
docker_socket_proxy_env_plugins:        0 # Not always needed
docker_socket_proxy_env_post:           0 # ⚠️ Security-critical
docker_socket_proxy_env_secrets:        0 # ⚠️ Security-critical
docker_socket_proxy_env_services:       0 # Not always needed
docker_socket_proxy_env_session:        0 # Not always needed
docker_socket_proxy_env_swarm:          0 # Not always needed
docker_socket_proxy_env_system:         0 # Not always needed
docker_socket_proxy_env_tasks:          0 # Not always needed
docker_socket_proxy_env_version:        1 # ✔️ Granted by default
docker_socket_proxy_env_volumes:        0 # Not always needed
```

Dependencies
------------

This role depends on :
- [djuuu.docker_project](https://github.com/Djuuu/ansible-role-docker-project)

Example Playbook
----------------

```yaml
---
- name: Install docker-socket-proxy
  hosts: all
  gather_facts: false

  roles:
    - djuuu.docker_socket_proxy
```

License
-------

Beerware License
