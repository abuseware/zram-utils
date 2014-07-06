ZRAM Utilities
==============
Two ASH/BASH/ZSH compatible scripts operating on ZRAM Linux module.

ZDISK
-------------
This script provides "ramdisk" drives with permament storage dump on shutdown.

**USAGE:** zdisk.sh <start|stop> zram[0-9]

On start:

  * Load file stored in /var/lib/zdisk/zram[0-9] into zram drive
  * Mount it at /mnt/zdisk/zram[0-9]

On shutdown:

  * Unmounts zram drive
  * Save drive state into file
  * Free zram drive

ZSWAP
------------
This script provides zram based swap device (compressed RAM like old compcache)

**USAGE:** zswap.sh <start|stop> zram[0-9]

On start:

  * Prepares zram drive with half of avaible RAM memory as swap.
  * Turn on zram swap space with maximum priority

On stop:

  * Turn off zram swap space
  * Free zram drive
