# netconsd

Role for deploy netconsd - The Netconsole Daemon

## Requirements

* Ansible 3.0.0+;

## Example configuration

```yaml
---
netconsd:
# Enable netconsd service or not
- enable: 'true'
# Restart netconsd service after deploy or not
  restart: 'true'
# Install netconsd package or not
  install_package: 'true'
# 'present' (do nothing if package is already installed) or 'latest' (always
# upgrade to last version)
  package_state: 'latest'
  settings:
# If you run out of memory and OOM, you need more workers (defaul is '2')
    - workers: '2'
# if you see messages being dropped, you need more listeners (default is '1')
      listeners: '1'
      mmsg_batch: ''
# Address for listen (default is listen on all addresses)
      listen_address: '192.168.0.254'
# Port to listen (default is '1514')
      listen_port: '1514'
# Output modules. By default in package avail 'logger.so' and 'printer.so'
      module:
        - 'logger.so'
```
