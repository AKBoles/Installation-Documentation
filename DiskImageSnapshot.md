CREATING A WHOLE DISK IMAGE SNAPSHOT OF Ubuntu 14.04 INSTANCE:
=============================================================

If required, install required dependencies:

    $ sudo apt-get install libguestfs-tools

Create a tar file of the contents of your instance (may take a few minutes):

    $ sudo tar cf /tmp/snapshot.tar / --selinux --acls --xattrs --numeric-owner --one-file-system --exclude=/tmp/* --exclude=/proc/* --exclude=/boot/extlinux

Next, convert the tar file into a qcow2 image:

    $ sudo virt-make-fs --partition --format=qcow2 --type=ext4 --label=`ls /dev/disk/by-label` /tmp/snapshot.tar /tmp/snapshot.qcow2

Update guestfs appliances (prevent an error with virt-make-fs):

    $ sudo update-guestfs-appliance

Next ensure that the GRUB bootloader is present in the image:

    $ sudo guestfish -a /tmp/snapshot.qcow2 -i sh 'grub-install /dev/sda && grub-mkconfig -o /boot/grub/grub.cfg'

To remove unwanted configuration information from your image, run:

    $ sudo virt-sysprep -a /tmp/snapshot.qcow2

To complete the preparation of your snapshot image, create a compressed version of it (This can decrease the size of your image on disk by a factor of 5 or more.):

    $ sudo qemu-img convert /tmp/snapshot.qcow2 -O qcow2 /tmp/snapshot_compressed.qcow2 -c

The final steps are to upload your snapshot image to OpenStack Glance. First, visit the Access & Security tab in the OpenStack web interface, navigate to the API Acess tab and press "Download OpenStack RC File". Copy this file to your instance and source it. Then simply use the glance client program to upload your image. NOTE: change name if desired!! Also do not use sudo on the following command!

    $ glance image-create --name my-snapshot --disk-format qcow2 --container-format bare < /tmp/snapshot_compressed.qcow2

