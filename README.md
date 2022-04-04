system_copy
=========

This role allows you to use the ansible.builtin.copy module to copy files.

Requirements
------------

ansible >= 2.10

Role Variables
--------------

```yml
system_copy:
  first_entry:
    attributes: ...
    backup: ...
    checksum: ...
    content: ...
    decrypt: ...
    dest: ...
    directory_mode: ...
    follow: ...
    force: ...
    group: ...
    local_follow: ...
    mode: ...
    owner: ...
    remote_src: ...
    selevel: ...
    serole: ...
    setype: ...
    seuser: ...
    src: ...
    unsafe_writes: ...
    validate: ...
  second_entry:
    .
    .
    .
  .
  .
  .
```

Dependencies
------------

None

Example Playbook
----------------

#### Copy a file with owner and permisssions:
```yml
- hosts: servers
  vars:
    system_copy:
      file1:
        src: /srv/myfiles/foo.conf
        dest: /etc/foo.conf
        owner: foo
        group: foo
        mode: '0644'
```

#### Copy using inline content and a new sudoers file into place, with validation
```yml
- hosts: servers
  vars:
    system_copy:
      file2:
        src: /srv/myfiles/foo.conf
        dest: /etc/foo.conf
        owner: foo
        group: foo
        mode: '0644'
      file3:
        src: /mine/sudoers
        dest: /etc/sudoers
        validate: /usr/sbin/visudo -csf %s
```
License
-------

GPL-3.0-only

Author Information
------------------

Role created by Turcu Mihai Ioan
