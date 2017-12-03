# ansible-go

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-go.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-go)

ansible role to install Go.

https://galaxy.ansible.com/suzuki-shunsuke/go/

## Requirements

Nothing.

## Role Variables

name | required | default | description
--- | --- | --- | ---
go_version | yes |  | Installed Go version
go_os | no | linux | OS type ("linux", "darwin", "freebsd", "windows")
go_arch | no | amd64 | "amd64" or "386" or "armv6l" or "s390x"
go_bin_dir | no | /usr/local/bin |
go_lib_dir | no | /usr/local/lib |
go_create_link | no | yes | whether create symbolic links or not

## Directory Structure

```
{{go_lib_dir}}/
  go-{{go_version}}/
    bin/
      go
      godoc
      gofmt
  go/ -> {{go_lib_dir}}/go-{{go_version}} (symbolic link)
{{go_bin_dir}}/
  go -> {{go_lib_dir}}/go/bin/go (symbolic link)
  godoc -> {{go_lib_dir}}/go/bin/godoc (symbolic link)
  gofmt -> {{go_lib_dir}}/go/bin/gofmt (symbolic link)
```

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: suzuki-shunsuke.go
      go_version: 1.9.2
      become: yes
```

## License

[MIT](LICENSE)
