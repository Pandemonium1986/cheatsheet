# Msys2 : Installation et Configuration

### Tool Versions

|         Os / Tool        |  Version |
| :----------------------: | :------: |
| Windows 10 Professionnel |   20H2   |
|           Msys2          | 20210419 |

### Installation procedure

Start by getting and installing the [Msys2](https://repo.msys2.org/distrib/x86_64/msys2-x86_64-20210419.exe) binary

Run the installer and follow the steps. Make sure to install MSYS2 in your user directory. `C:\Users\USER_NAME\.msys64`

![msys2-001](./img/msys2-001.png)

![msys2-002](./img/msys2-002.png)

![msys2-003](./img/msys2-003.png)

![msys2-004](./img/msys2-004.png)

![msys2-005](./img/msys2-005.png)

![msys2-006](./img/msys2-006.png)

### Post installation procedure

Run `MSYS2 MinGW 64-bit`  

If you are behind a proxy configure it from the command line to start:

```sh
export http_proxy="http://LOGIN:PASSWORD@PROXY:PORT" && export https_proxy=$http_proxy && curl -ivks https://github.com
```

In case of TLS proxy get the root and intermediate authorities and add them.

```sh
mkdir ~/certs
# Retrieving certificates
trust anchor --store ~/certs/cert001.crt
# [...]
trust anchor --store ~/certs/certXXX.crt
update-ca-trust
```

Update the system

```sh
pacman -Syu
```

Install the base-devel and mingw-w64-x86_64-toolchain packages

```sh
pacman -S --needed base-devel mingw-w64-x86_64-toolchain
# [...] output truncated
Enter a selection (default=all): 1-48
# [...] output truncated
Enter a selection (default=all): 1-19
# [...] output truncated
:: Proceed with installation? [Y/n] Y
```

### Specific installation procedure


### Source

[GitHub - Msys2 installer](https://github.com/msys2/msys2-installer)  
[Msys2 - Website](https://www.msys2.org/)  
