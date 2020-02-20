# Add a block device as a cache device to an existing pool

Pools may optionally contain a cache tier, which contains up to 8 blockdevs used for caching. Cache devices are typically smaller and faster than data devices, and so solid-state drives (SSDs) make good cache devices.

For the purposes of this example, we will use our loop3 device to demostrate.

Add /dev/loop3 as a cache device to my_pool.

`stratis pool add-cache my_pool /dev/loop3` {{execute}}
