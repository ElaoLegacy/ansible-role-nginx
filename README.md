WARNING: This role is no longer maintained !!!
==============================================

You are strongly encouraged to switch to the new roles stack on https://github.com/ElaoInfra
--------------------------------------------------------------------------------------------

By the way, this role will remain available on https://github.com/ElaoLegacy
----------------------------------------------------------------------------


Ansible Role - Nginx
====================

A nginx role for installing and configuring Nginx

Role Handlers
-------------

    nginx restart  # Restart nginx service

Role Variables
--------------

    All those values are default configuration, specify them only if you need to override the default configuration.

#### Sample configuration:

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
    sendfile:                    "on"
    tcp_nopush:                  "on"
    tcp_nodelay:                 "on"
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

    default_type:                "text/html"
    access_log:                  "/var/log/nginx/access.log"
    error_log:                   "/var/log/nginx/error.log"

elao_nginx_config_gzip:
    gzip:                        "on"
    gzip_disable:                "msie6"
    gzip_vary:                   "on"
    gzip_proxied:                "any"
    gzip_comp_level:             6
    gzip_buffers:                "16 8k"
    gzip_min_length:             4096
    gzip_http_version:           "1.1"
    gzip_types:                  "text/plain text/css application/json application/x-javascript text/xml application/xml application/xml+rss text/javascript;"
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
