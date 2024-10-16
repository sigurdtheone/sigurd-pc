
# Media Codecs:

```bash
sudo dnf swap ffmpeg-free ffmpeg --allowerasing
sudo dnf update @multimedia --setopt="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
sudo dnf update @sound-and-video
sudo dnf install libdvdcss
```

# Steam

These will need you to have all downloads paused (unpause the download after entering the command) and the steam console opened (openable with steam://open/console in your web browser).

HTTP2 disabling

```
@nClientDownloadEnableHTTP2PlatformLinux 0 
```

(https://www.reddit.com/r/linux_gaming/comments/16e1l4h/slow_steam_downloads_try_this/)


# Samba

```bash
sudo dnf install cifs-utils
sudo mkdir -p /mnt/Steffi
sudo mkdir -p /mnt/Navi
sudo vim /etc/fstab
sudo vim /etc/samba/credentials
sudo chmod 600 /etc/samba/credentials
sudo mount -a
```

```
//10.8.0.10/Navi /mnt/Navi cifs credentials=/etc/samba/credentials,uid=1000,gid=1000 0 2
//10.8.0.10/Steffi /mnt/Steffi cifs credentials=/etc/samba/credentials,uid=1000,gid=1000 0 2
```

# Graphics

```bash
sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld
sudo dnf swap mesa-vdpau-drivers mesa-vdpau-drivers-freeworld
sudo dnf swap mesa-va-drivers.i686 mesa-va-drivers-freeworld.i686
sudo dnf swap mesa-vdpau-drivers.i686 mesa-vdpau-drivers-freeworld.i686
```

# LVM Cache HDD

```bash
wipefs --all --backup /dev/sdb
pvcreate /dev/sdb
pvcreate /dev/nvme1n1p3
vgcreate vg_data /dev/sdb /dev/nvme1n1p3
lvcreate -L 9t -n lv_data vg_data /dev/sdb
lvcreate -n cachepool_meta -L 1G vg_data /dev/nvme1n1p3
lvcreate -n cachepool -L 400G vg_data /dev/nvme1n1p3
lvconvert --type cache-pool --poolmetadata cachepool_meta vg_data/cachepool
lvconvert --type cache --cache-pool cachepool --cachemode writethrough vg_data/lv_data
```

(https://blog.delouw.ch/2020/01/29/using-lvm-cache-for-storage-tiering/)


# Misc Software

## Utils

```bash
sudo dnf install mediainfo htop nvtop iotop
```
## CoolerControl

```bash
# make sure you have the necessary plugin:
sudo dnf install dnf-plugins-core
sudo dnf copr enable codifryed/CoolerControl
sudo dnf install coolercontrol
sudo systemctl enable --now coolercontrold
```

# Bluetooth

Connecting bluetooth devices (ps5 controller) and similar.

```bash
bluetoothctl
[bluetooth]# power on
[bluetooth]# help
[bluetooth]# scan on
[bluetooth]# pair <dev>
[bluetooth]# trust <dev>


