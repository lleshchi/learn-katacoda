# Add a block device as a data device to an existing pool

All pools contain a data tier, which contains one or more blockdevs used to store data. The blockdev used to create the pool belongs to the pool's data tier. We can add additional blockdevs to a pool as a data device.

Add /dev/loop2 as a data device to my_pool.

`stratis pool add-data my_pool /dev/loop2`{{execute}}

If you list your pool, it should now have a size of 20GiB

`stratis pool list` {{execute}}
