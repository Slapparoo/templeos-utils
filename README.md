# templeos-utils
TempleOS utils

A set of basic linux utilities for running TempleOS and mounting the image locally
qemu
Virtual Box

Don't run the virtual macine with the drives mounted, unmount before starting your virtual machine

Once the drives are mounted you can copy files to and from their drive with standard cp i.e
`cp -r /mnt/vtosee_diskd/* localcopy`
or
`cp localcopy/Home/MyCode.HC /mnt/vtosee_diskd/Home`

or after running a DoDistro.HC
`cp /mnt/vtosee_diskd/Tmp/MyDistro.OSO.C MyDistro.iso`

For the q-backup* scripts there is no corrosponding restore (I haven't needed one yet), but it pleases me to know they are backed up. 

After probing and before mounting you can reformat a partition with 
`sudo modprobe nbd max_part=16`
`sudo qemu-nbd -c /dev/nbd0 ~/tos_disk.qcow2`
`sudo partprobe /dev/nbd0`
(be careful, make sure you have the correct /dev/<name> as things can go wrong if you don't) /dev/nbd0p2 is the d drive
`sudo mkfs -t vfat /dev/nbd0p2`


