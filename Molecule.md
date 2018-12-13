# Molecule : Installation et Configuration

### Version des outils

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   1803  |
|  Wsl - Debian GNU/Linux  |  9.5.0  |
|          Ansible         |   2.6+  |
|         Molecule         |  2.1.9+ |

### Procédure d'installation

La procédure d'installation de _Molecule_ sur _Debian 9.5.0_ se déroule de la façon suivante :
**Attention** installer molecule via pip install la dernière version d'ansible.

```sh
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
sudo apt install python-dev
sudo python get-pip.py
sudo pip install molecule
sudo pip install molecule --ignore-installed -U PyYAML
```

### Source

[Molecule Read the docs](https://molecule.readthedocs.io/en/latest/)
[Molecule Github](https://github.com/ansible/molecule)
