# Mine Debian without GUI
Custom debian iso for automatic mining without GUI for better performance

## How to
I recommend use Debian Buster.
1. Install dependecies
`sudo apt install -y live-build`
2. Configure the live-build
`lb config --archive-areas "main contrib non-free" --distribution buster --debian-installer-distribution buster --bootappend-live "boot=live components hostname=live-mine-debian"`
3. Build the image
`lb build`
### Netboot (optional)
1. Mount builded iso file
`sudo mount -o loop live-image-amd64.hybrid.iso /media/cdrom`
2. Copy files from mounted iso file to your tftp / http(s) server root
`cp /media/cdrom/live/vmlinuz /media/cdrom/live/initrd.img /media/cdrom/live/filesystem.* /your/path/ -f`
3. Unmount mounted iso file
`sudo umount /media/cdrom`
