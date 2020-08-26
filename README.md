# ansible-role-apache_proxy

[![Build Status](https://travis-ci.org/jewflix/ansible-role-apache_proxy.svg?branch=master)](https://travis-ci.org/jewflix/ansible-role-apache_proxy)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-apache_proxy-blue.svg?style=flat)](https://galaxy.ansible.com/jewflix/apache_proxy)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RedHat - Apache Proxy Server

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    apache_proxy_group: apache
    apache_proxy_listen:
      - 443
    apache_proxy_modules:
      - auth_basic
      - authn_core
      - authn_file
      - authz_core
      - authz_user
      - headers
      - mpm_worker
      - proxy
      - proxy_html
      - proxy_http
      - proxy_wstunnel
      - ssl
      - systemd
      - unixd
      - xml2enc
    apache_proxy_packages:
      - httpd
      - mod_ssl
      - mod_proxy_html
    apache_proxy_server:
      admin: heeb@jewflix.studio
      name: jewflix.studio
      root: /etc/httpd
      tokens: ProductOnly
    apache_proxy_user: apache
    apache_proxy_vhosts: []

## Dependencies

None

## Example Playbook

    - hosts: jewflix
      roles:
        - role: jewflix.apache_proxy
          apache_proxy_vhosts:
            - name: proxy.jewflix.studio
              port: 8080

## License

Copyright (C) 2020 Jewflix Studios

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
