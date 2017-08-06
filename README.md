# Steam on FreeBSD 11.0

You need to have a recent nvidia-driver with LINUX compatibality support or an AMD graphics card that is supported by FreeBSD. See [FreeBSD Wiki](https://wiki.freebsd.org/Graphics) for further information. 

nvidia-driver or xf86-video-ati

## Dependencies

`pkg install deb2targz rpm2cpio doas`

Create /usr/local/etc/doas.conf :

`touch /usr/local/etc/doas.conf`

And add:

`echo 'permit nopass keepenv <<yourusername>>' >> /usr/local/etc/doas.conf`

Where <<yourusername>> is the user name on which you want to install and run Steam.

## Download Steam

`fetch  http://media.steampowered.com/client/installer/steam.deb`

Convert it in to tar.gz:

`deb2targz steam.deb`

Extract steam.tar.gz as root:

`tar -zxvf steam.tar.gz -C /compat/linux/`

## Setting up SteamOnFreeBSD

`git clone https://github.com/SteamOnFreeBSD/SteamOnFreeBSD.git`

`cd SteamOnFreeBSD`

`steam`

### On i386

In script steamrun change variable ubuntu to ubuntu

`./install.sh`
`./steamrun`

### On amd64

In script steamrun change variable ubuntu to ubuntu_x86_64

`./install.sh`
`./install_x86_64.sh`
`./steamrun`

-----

![alt tag](https://raw.githubusercontent.com/SteamOnFreeBSD/Steam/master/2016-03-15-171059_1366x768_scrot.png)
![alt tag](https://raw.githubusercontent.com/SteamOnFreeBSD/Steam/master/2016-04-03-030913_1366x768_scrot.png)
