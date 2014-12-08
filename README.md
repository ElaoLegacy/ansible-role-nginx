Ansible Role - Nginx
====================

A nginx role for installing and configuring Nginx

Role Handlers
-------------

    nginx restart  # Restart nginx service


Role Variables
--------------

    All those values are default configuration, specify them only if you need to override the default configuration.

```
elao_nginx_config_global:
    worker_processes:            2
    user:                        www-data
    pid:                         "/var/run/nginx.pid"

elao_nginx_config_events:
    worker_connections:          768
    multi_accept:                "on"
    use_epoll:                   yes

elao_nginx_config_http:
    keepalive_timeout:           "65s"
    client_body_timeout:         "60s"
    client_header_timeout:       "60s"
    client_body_buffer_size:     "8k"
    client_header_buffer_size:   "1k"
    client_max_body_size:        "1m"

    large_client_header_buffers: "4 8k"
    send_timeout:                "60s"
    reset_timedout_connection:   "off"
    types_hash_max_size:         1024
    server_tokens:               "on"

    types_hash_max_size:         1024
    default_type:                "text/html"
    access_log:                  "/var/log/nginx/access.log"
    error_log:                   "/var/log/nginx/error.log"
```

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: elao.nginx }

License
-------

MIT


Author Information
------------------

http://www.elao.com/
