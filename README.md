go
=========

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-go.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-go)

Install Go on Linux.

https://galaxy.ansible.com/suzuki-shunsuke/go/

Requirements
------------

Nothing.

Role Variables
--------------

* go_nonroot: Whether the remote_user is root or not. This variable is set automatically, and is used to execute tasks with the become option.
* go_version: The Go version. The default value is 1.7.1.
* go_os: The OS type("linux", "darwin", "freebsd", "windows"). The default value is "linux".
* go_arch: "amd64" or "386" or "armv6l" or "s390x". The default value is "amd64".

Dependencies
------------

Nothing.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.go
    go_version: 1.6.1
```

License
-------

MIT
