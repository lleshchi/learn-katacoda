# Destroy a filesystem

To destroy a filesystem, you'll first want to ensure that it's not in use. Since we mounted our filesystem previously, we will need to unmount it.

`umount /mnt/test_mnt`{{execute}}

Then, execute the following command.

`stratis filesystem destroy my_pool my_fs`{{execute}}

# Destroy a snapshot

To destroy a snapshot, execute the following command.

`stratis filesystem destroy my_pool my_snapshot`{{execute}}

# Destroy a pool

To destroy a pool, you'll first want to ensure that it does not contain any filesystems. Then, execute the following command.

`stratis pool destroy my_pool`{{execute}}
