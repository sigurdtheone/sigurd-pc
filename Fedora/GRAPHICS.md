# Setting up Graphics

Most of this will focus on AMD and the 7900 XTX


## Installing Mesa Drivers

#!TODO: Why swap?:/

```bash
sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld
sudo dnf swap mesa-vdpau-drivers mesa-vdpau-drivers-freeworld
sudo dnf swap mesa-va-drivers.i686 mesa-va-drivers-freeworld.i686
sudo dnf swap mesa-vdpau-drivers.i686 mesa-vdpau-drivers-freeworld.i686
```

## Setting up monitoring Software

### Installing `amdgpu_top`

Go to this URL and grab the .rpm https://github.com/Umio-Yasuno/amdgpu_top/releases

Install with Software Centre

## Setting up LACT overclocking

### Installing LACT

?

```bash
sudo systemctl enable --now lactd
```

### Setting up OC for Sapphire 7900XTX Nitro+

![image](https://github.com/user-attachments/assets/765ce601-42ea-4d7e-842d-915bf9facaf2)
