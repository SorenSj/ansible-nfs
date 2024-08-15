Role Name
=========

Installs NFS utilities on RedHat/CentOS or Debian/Ubuntu.

Requirements
------------

None

Role Variables
--------------

- `nfs_version`: NFS version to use (default: nfs)
- `nfs_mount_opts`: Default NFS mount options (default: defaults)
- `nfs_share_mounts`: List of dictionaries of NFS shares:
  - `path`: mount-point
  - `mount`: nfs server path
  - `opts`: mount options (optional)
  - `nfs_version`: NFS version to use (optional; default to {{ nfs_version }})

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: localhost
  roles:
  - role: nfs
    nfs_share_mounts:
    - path: /mnt/remote
      location: nfs.example.org:/data
      nfs_version: nfs
    - path: /mnt/readonly
      location: nfs.example.org:/read-only
      opts: "{{ nfs_mount_opts }},ro"
      nfs_version: nfs4
```

License
-------

MIT

Author Information
------------------

soren.sjostrom@hotmail.com