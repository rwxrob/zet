# You Don't *Have* to Partition Volumes

Might be obvious, but you can use `mkfs -t ext4 -L /s /dev/sdb`
instead of `/dev/sdb1` if you want to avoid partitioning a disk that
doesn't need it. In a world of virtualization it is every bit as easy to
define a specific volume size without doing any partitioning at all. 

But *should* you drop partitioning?

To someone raised on hard-disks with partition tables this is somewhat
counter-intuitive (even feels dirty). One of the many ways a beginner
(like me once upon a time) can destroy a perfectly good disk is to leave
off the number of the partition (ex: `/dev/sdb` instead of `/dev/sdb1`).
For this reason, I feel like taking the unnecessary step of creating a
single partition for the entire drive will seem more normal to admins
old and young. I'm not sure I want to encourage people to ever stop
paying attention to the numbers of the partitions just for the
safety-net it provides.

Of course, using `lsblk` is definitely the way to go to avoid all of
this confusion, but having a partition table might still avoid some
mishaps.
