# Ansible Role: etc_hosts

An Ansible role that allows to add or remove entries in the /etc/hosts file and in Unbound if needed.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    etc_hosts: []                              # the list of hostnames
      - hostname: [mandatory]                  # one or more hostnames
        address: [mandatory]                   # the ip adress
        state: present                         # present|absent
    
    etc_hosts_unbound_file: [optional]         # the name of the file where the Unbound configuration will be stored                     
    
The list of entries to add to /etc/hosts and in Unbound the `etc_hosts_unbound_file` variable is defined.
Each item must include one or more `hostname(s)` and the assiocated IP `address`. 

## Dependencies

None.

## Example Playbook

    - hosts: webservers
      roles:
        - role: t18s.fr_etc_hosts
          etc_hosts:
            - hostname: xxxxxx
              address: xx.yy.xx.yy
              state: present
              
## Todo

None.

## License

```
Copyright (c) 2018, 2019 Tristan Weil <titou@lab.t18s.fr>

Permission to use, copy, modify, and distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```
