# Hey! I'm Filing Here

In this lab, I successfully implemented the following functions:
write_superblock
write_block_group_descriptor_table
write_block_bitmap
write_inode_bitmap
write_inode_table
write_root_dir_block
write_hello_world_file_block

The given skeleton code plus these functions created a 1MiB ext2 file system with 2 directories, 1 regular file, and 1 symbolic link.

## Building
To build, simply run the command
```shell
make
```
## Running
To create the image of the filesystem (cs111-base.img) use
```shell
./ext2-create
```
The specs can then be checked with for more information:
```shell
dumpe2fs cs111-base.img
```
And this command will pass the file system 5 times checking for errors:
```shell
fsck.ext2 cs111-base.img
```
Finally this will show the directories and files in our filesystem
```shell
mkdir mnt
sudo mount -o loop cs111-base.img mnt
ls -ain mnt
```
## Cleaning up
To remove the executables, run:
```shell
make clean
```
Unmount and remove the mounted filesystem:
```shell
sudo unmount mnt
rmdir mnt
```
