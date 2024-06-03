
# Media Codecs:

```shell
sudo dnf swap ffmpeg-free ffmpeg --allowerasing
sudo dnf update @multimedia --setopt="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
sudo dnf update @sound-and-video
sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld
sudo dnf swap mesa-vdpau-drivers mesa-vdpau-drivers-freeworld
sudo dnf swap mesa-va-drivers.i686 mesa-va-drivers-freeworld.i686
sudo dnf swap mesa-vdpau-drivers.i686 mesa-vdpau-drivers-freeworld.i686
sudo dnf install rpmfusion-free-release-tainted
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

```yaml
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
