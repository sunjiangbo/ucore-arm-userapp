uClibc

cp ./uclibc_config.linuxthread ./uClibc-0.9.33/.config
make menuconfig

Target Arch Features and Options -> Linux kernel header locate
set to `pwd`/linux_header_goldfish/include

Library Installation Options
uClibc runtime libarary directory: `pwd`/install
uClibc development env dir: `pwd`/install/usr

make -j6
make install


MiniGUI

source env.sh
(you may need to modify GCC_LIB in env.sh)
cd ./libminigui-gpl-3.0.12/ 
./configure --prefix=$(readlink -f $(pwd)/../install) --host=arm-linux --disable-videoqvfb --disable-pcxvfb --disable-shared --disable-dlcustomial --disable-jpgsupport --disable-pngsupport --disable-flatlf --disable-skinlf --enable-videogoldfish --enable-goldfishial

Ignore the error "./configure: line 15636: ./runme.sh: No such file or directory"

make -j8
make install

you might need the resource package, download it from minigui.com
install into ./install

Now, you get every thing you need in ./install
