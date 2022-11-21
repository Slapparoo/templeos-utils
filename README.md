# templeos-utils
TempleOS utils

A set of basic linux utilities for running TempleOS and mounting the image locally for:
* qemu
* Virtual Box

To help avoid disk or file corruption don't run the virtual macine with the drives mounted:
* unmount before starting your virtual machine.
* Stop your virtual machine before mounting.

Once the drives are mounted you can copy files to and from their drive with standard cp i.e<br/>
`cp -r /mnt/vtosee_diskd/* localcopy`<br/>
Will copy every thing from the TempleOS d drive into a local folder called localcopy (which will need to exist before copying).<br/> 
or<br/>
`cp localcopy/Home/MyCode.HC /mnt/vtosee_diskd/Home`<br/>
Will copy a local file onto the TempleOS d drive</b>

or after running a DoDistro.HC<br/>
`cp /mnt/vtosee_diskd/Tmp/MyDistro.OSO.C MyDistro.iso`

For the q-backup* scripts there is no corrosponding restore (I haven't needed one yet), but it pleases me to know they are backed up. <br/>

After probing and before mounting you can reformat a partition with<br/> 
`sudo modprobe nbd max_part=16`<br/>
`sudo qemu-nbd -c /dev/nbd0 ~/tos_disk.qcow2`<br/>
`sudo partprobe /dev/nbd0`<br/>
(be careful, make sure you have the correct /dev/<name> as things can go wrong if you don't) /dev/nbd0p2 is the d drive<br/>
`sudo mkfs -t vfat /dev/nbd0p2`

These are companion utilities for TempleOS and should be usable far any flavour

See the main [TempleOS-EE main project](https://slapparoo.github.io/TempleOS-EE/)


