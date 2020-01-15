# Molecule: Installation and Configuration

## Tools versions

|  Os / Tool | Version |
| :--------: | :-----: |
| Linux Mint |   19.3  |
|   Ansible  |  2.9.2  |
|  Molecule  |   2.22  |

## Todo

N/A

## Bulk Note

N/A

## About

> Molecule is designed to aid in the development and testing of Ansible roles.
> Molecule provides support for testing with multiple instances, operating systems and distributions, virtualization providers, test frameworks and testing scenarios.
> Molecule encourages an approach that results in consistently developed roles that are well-written, easily understood and maintained.

## Installation procedure

**Centos requirements**

```sh
sudo yum install -y epel-release
sudo yum install -y gcc python-pip python-devel openssl-devel libselinux-python
```

**Debian requirements**

```sh
sudo apt-get update
sudo apt-get install -y python-pip libssl-dev
```

**Molecule**

```sh
pip install --upgrade --user setuptools
pip install --user molecule
```

**Docker**

```sh
docker pull quay.io/ansible/molecule:2.22
```

## Getting start

**Creating a new role**

```sh
molecule init role -r my-new-role
```

**Molecule Scenario**

After init role there is a molecule folder wich containes a default folder wich is the default scenario. In this scenario we can found :

-   _Dockerfile.j2_ Jinja2 template file in place. Molecule will use this file to build a docker image to test your role against.
-   _INSTALL.rst_ contains instructions on what additional software or setup steps you will need to take in order to allow Molecule to successfully interface with the driver.
-   _molecule.yml_ is the central configuration entrypoint for Molecule.
-   _playbook.yml_ is the playbook file that contains the call site for your role.
-   tests is the tests directory created because Molecule uses TestInfra as the default Verifier.

**Molecule.yml**

The molecule.yml is for configuring Molecule. It is a YAML file whose keys represent the high level components that Molecule provides. These are:

-   The Dependency manager.
-   The Driver provider.
-   The Lint provider.
-   The Platforms definitions.
-   The Provisioner. Molecule only provides an Ansible provisioner.
-   The Scenario definition.
-   The Verifier framework.

**Run test sequence commands**

```sh
# Create instance
molecule create

# List instance
molecule list

# Execute playbook
molecule converge

# Inspect instance
molecule login

# Destroy instance
molecule instance
```

**Run a full test sequence**

```sh
molecule test
```

## Usage

-   **check**        Use the provisioner to perform a Dry-Run...
-   **cleanup**      Use the provisioner to cleanup any changes...
-   **converge**     Use the provisioner to configure instances...
-   **create**       Use the provisioner to start the instances.
-   **dependency**   Manage the role's dependencies.
-   **destroy**      Use the provisioner to destroy the instances.
-   **idempotence**  Use the provisioner to configure the...
-   **init**         Initialize a new role or scenario.
-   **lint**         Lint the role.
-   **list**         Lists status of instances.
-   **login**        Log in to one instance.
-   **matrix**       List matrix of steps used to test instances.
-   **prepare**      Use the provisioner to prepare the instances...
-   **side-effect**  Use the provisioner to perform side-effects...
-   **syntax**       Use the provisioner to syntax check the role.
-   **test**         Test (lint, cleanup, destroy, dependency,...
-   **verify**       Run automated tests against instances.

## Source

[Molecule Read the docs](https://molecule.readthedocs.io/en/latest/)
[Molecule Github](https://github.com/ansible/molecule)
[Molecule Docker images](https://quay.io/repository/ansible/molecule)
