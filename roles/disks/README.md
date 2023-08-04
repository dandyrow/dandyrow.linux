Ansible Role - Disks
====================

Define disk layout as yaml to create partitions then format and mount them.

Disks can also be formatted and mounted without creating partitions.

Make sure if not partitoning disks don't define part_number and only define one
layout item. If defining partitons make sure to include part_number for each
list item or you may experience unexpected behaviour.

Example Playbook
----------------

Below is an example playbook. It creates a standard linux disk structure on
the disk /dev/sda with 3 partitions and mounts the entire disk without partition
of nvme0n1.

```yaml
    - hosts: servers
      roles:
        - role: dandyrow.linux.disks
          vars:
            disks:
              - dev_path: /dev/sda
                layout:
                  - part_number: 1
                    part_end: 512MiB
                    fs_type: vfat
                    fs_options: -F 32
                    mount_path: /mnt/efi
                  - part_number: 2
                    part_end: 512MiB
                    part_start: 80%
                    fs_type: ext4
                    mount_path: /mnt
                  - part_number: 3
                    part_start: 80%
                    part_fs_type: linux-swap
                    fs_type: swap
                    mount_path: none
                    mount_options: defaults
              - dev_path: /dev/nvme0n1
                layout:
                  - fs_type: ext4
                    mount_path: /mount
```
License
-------

GPL-3.0-only
