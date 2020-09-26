# Ansible Role: etc_hosts

An Ansible Role that allows to add or remove entries in the /etc/hosts file and in Unbound if needed.

**NOTE**: it does not work on Docker.

[![Actions Status](https://github.com/tristan-weil/ansible-role-etc_hosts/workflows/molecule/badge.svg?branch=master)](https://github.com/tristan-weil/ansible-role-etc_hosts/actions)

## Role Variables

Available variables are listed below, (see also `defaults/main.yml`).

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| etc_hosts     | []      | a list of <*etc_host*> entries |

### <*etc_host*>

A *etc_host* represents an entry of one or more hostnames and an associated IP address.

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |
| hostname      | one or more hostnames |
| address       | an IP address |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| state         | present | *present / asbent*: the state of the entry in the `/etc/hosts` file |

## Example Playbook

    - hosts: 'webservers'
      roles:
        - role: 'ansible-role-etc_hosts'
          etc_hosts:
            - hostname: xxxxxx
              address: xx.yy.xx.yy
              state: 'present'
              
## Todo

None.

## Dependencies

None.

## Supported platforms

See [meta/main.yml](https://github.com/tristan-weil/ansible-role-etc_hosts/blob/master/meta/main.yml)

## License

See [LICENSE.md](https://github.com/tristan-weil/ansible-role-etc_hosts/blob/master/LICENSE.md)
