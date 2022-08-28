# WSL 2 Installation

## Activate the Windows subsystem for Linux

```sh
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

## Activate the Virtual Machine feature

```sh
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

## Download linux kernel update package 

- Download the lastest package:

[WSL 2 Linux kernel update package for x64 machines ](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

- Run the wsl_update_x64.msi file

## Set WSL 2 as default version

```sh
wsl --set-default-version 2
```

## Install Linux distribution

```sh
wsl --install -d Ubuntu
```

## Verify Linux installation

```sh
wsl --list --verbose
```

# References

- [wsl manual installation](https://docs.microsoft.com/fr-fr/windows/wsl/install-manual)