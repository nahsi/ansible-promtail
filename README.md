# promtail

Install, configure and maintain
[promtail](https://grafana.com/docs/loki/latest/clients/promtail/)

## Role Philosophy

Please see
[ansible-consul](https://github.com/nahsi/ansible-consul#role-philosophy).

## Role Variables

See [defaults/](https://github.com/nahsi/ansible-promtail/blob/master/defaults/)
for details and examples.

#### `promtail_version`

- version to use

#### `promtail_dirs`

- a map of directories to create
- default:

```yaml
promtail_dir: "/opt/promtail"
promtail_dirs:
  main:
    path: "{{ promtail_dir }}"
  logs:
    path: "/var/log/promtail"
```

#### `promtail_config`

- main
  [configuration](https://grafana.com/docs/loki/latest/clients/promtail/configuration/)
  file
- example: please see
  [defaults/example.yml](https://github.com/nahsi/ansible-promtail/blob/master/defaults/example.yml)

#### `promtail_user`

- owner of promtail process and files
- default: `promtail`

#### `promtail_group`

- group of `promtail_user`
- default: `promtail`

#### `promtail_download_url`

- url to get promtail archive from
- default: `https://releases.hashicorp.com`

#### `promtail_service`

- openrc service file
- default: see
  [defaults/main.yml](https://github.com/nahsi/ansible-promtail/blob/master/defaults/main.yml)

#### `promtail_unitfile`

- systemd unit file
- default: see
  [defaults/main.yml](https://github.com/nahsi/ansible-promtail/blob/master/defaults/main.yml)

#### `skip_handlers`

- skip restart/reload - useful when building images with Packer
- default: `false`

## Tags

- `config` - update promtail unit/service file and sync configuration files

## Author

- **Anatoly Laskaris** - [nahsi](https://github.com/nahsi)
