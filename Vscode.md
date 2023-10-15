# Visual Studio Code

## Tools versions

| Os / Tool  | Version |
| :--------: | :-----: |
| Linux Mint |  19.3   |
|   Vscode   | 1.63.2  |
|  Molecule  |  3.0.3  |

## How to install

```sh
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm -f packages.microsoft.gpg
```

```sh
sudo apt install apt-transport-https
sudo apt update
sudo apt install code # or code-insiders
```

## Configuration

Installation of extensions :

Installation of extensions :

```sh
code --install-extension bbenoist.vagrant --force
code --install-extension donjayamanne.python-environment-manager --force
code --install-extension EditorConfig.EditorConfig --force
code --install-extension iciclesoft.workspacesort --force
code --install-extension ms-azuretools.vscode-docker --force
code --install-extension ms-python.python --force
code --install-extension ms-vscode.atom-keybindings --force
code --install-extension redhat.ansible --force
code --install-extension redhat.vscode-yaml --force
code --install-extension yzhang.markdown-all-in-one --force
```

## Knowledge Base

### Cheat Sheet

## Source

[Visual Studio Code](https://code.visualstudio.com/)
[Debian and Ubuntu based distributions](https://code.visualstudio.com/docs/setup/linux#_debian-and-ubuntu-based-distributions)
[Keyboard Shortcuts Reference](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf)
