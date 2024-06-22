# Game Fixes for Various Games:


## Fallout 4

Launch Option: `gamescope -e -w 3840 -h 2160 -r 60 -f --force-grab-cursor -b --adaptive-sync -- %command%`

## Gamestutter after a while

https://github.com/ValveSoftware/gamescope/issues/163

Enable Steam overlay or `env LD_PRELOAD=""` in launch options.

## Minecraft

### Modpacks

Install prismlauncher instead of curseforge.

```bash
sudo dnf copr enable g3tchoo/prismlauncher
sudo dnf install prismlauncher
```

### Fix audio crash on some modpacks:

```bash
echo drivers=pulse,alsa >> ~/.alsoftrc
reboot
```

