I have updated UML to 5.6.2 here very crudely as it has only just released and wanted to get this to work as soon as possible. I incremented the kernel number inside debian/rules. I then cloned the linux source 5.6.2 to /usr/src (as this is where the makefile usually expects the source to be.)

wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.6.2.tar.xz

Rename this folder and the folder inside the archive to linux-source-5.6.2.tar.xz and linux-source-5.6.2

Inside config.i386, 
CONFIG_SLAB=y
CONFIG_SLUB=n
due to a kernel panic caused by SLUB.

CONFIG_WIREGUARD has also been set to y due to our usecase.

command.sh can be used to extract the source from /usr/src into the top directory.

The makefiles have been modified slightly to get this all to work.
