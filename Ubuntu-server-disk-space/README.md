# Ubuntu server installation use entire disk space
During Ubuntu server installation, there is an important step to set the
disk partition size. Usually, there is a partition for boot and another
partition for the rest of the disk space. However, I have noticed that
the drive size partition for the lvm ext4 size doesn't take up maximum
space. For example if the space allocated is 15G and 1.6G has been
allocated to boot partition, the ext4 defaults the other partition size
to be 10G. Missing out 3G of space.

To make use of maximum disk space, edit the size manually. There will be
a prompt that lists the maximum size available and enter that number to
make full use of the disk space.

This will save a lot of time later on when you realise you do need the
additional space and have to manually enlarge the partition.

Related:
* [Youtube install
      video](https://www.youtube.com/watch?v=zs2zdVPwZ7E&t=580s)
* [Rob's zet to enlarge partition size](https://github.com/rwxrob/zet/blob/e0800f0a37d3918ddf90dcca5654df56d247ab97/20220714191155/README.md)

Tags:

    #ubuntu #install #disk #storage

Timestamp:
    20221002141019