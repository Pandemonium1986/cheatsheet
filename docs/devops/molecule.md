<!-- markdownlint-disable MD036 -->
# Molecule: Installation and Configuration

## Tools versions

|  Os / Tool | Version |
| :--------: | :-----: |
| Linux Mint |   19.3  |
|   Ansible  |  2.9.6  |
|  Molecule  |  3.0.3  |

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
sudo yum install -y gcc python3-pip python3-devel openssl-devel libselinux-python
```

**Debian requirements**

```sh
sudo apt-get update
sudo apt-get install -y python3-pip libssl-dev
```

**Molecule**

```sh
python3 -m pip install --upgrade --user setuptools
python3 -m pip install --user "molecule[lint]"
```

**Docker**

```sh
docker pull quay.io/ansible/molecule:3.0.3
```

## Getting start

**Creating a new role**

```sh
molecule init role -r my-new-role
```

**Molecule Scenario**

After init role there is a molecule folder wich containes a default folder wich is the default scenario. In this scenario we can found :

- _Dockerfile.j2_ Jinja2 template file in place. Molecule will use this file to build a docker image to test your role against.
- _INSTALL.rst_ contains instructions on what additional software or setup steps you will need to take in order to allow Molecule to successfully interface with the driver.
- _molecule.yml_ is the central configuration entrypoint for Molecule.
- _converge.yml_ is the playbook file that contains the call site for your role.
- tests is the tests directory created because Molecule uses TestInfra as the default Verifier.

**Molecule.yml**

The molecule.yml is for configuring Molecule. It is a YAML file whose keys represent the high level components that Molecule provides. These are:

- The Dependency manager.
- The Driver provider.
- The Lint provider.
- The Platforms definitions.
- The Provisioner. Molecule only provides an Ansible provisioner.
- The Scenario definition.
- The Verifier framework.

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
molecule destroy
```

**Run a full test sequence**

```sh
molecule test
```

## Usage

- **check**        Use the provisioner to perform a Dry-Run...
- **cleanup**      Use the provisioner to cleanup any changes...
- **converge**     Use the provisioner to configure instances...
- **create**       Use the provisioner to start the instances.
- **dependency**   Manage the role's dependencies.
- **destroy**      Use the provisioner to destroy the instances.
- **idempotence**  Use the provisioner to configure the...
- **init**         Initialize a new role or scenario.
- **lint**         Lint the role.
- **list**         Lists status of instances.
- **login**        Log in to one instance.
- **matrix**       List matrix of steps used to test instances.
- **prepare**      Use the provisioner to prepare the instances...
- **side-effect**  Use the provisioner to perform side-effects...
- **syntax**       Use the provisioner to syntax check the role.
- **test**         Test (lint, cleanup, destroy, dependency,...
- **verify**       Run automated tests against instances.

## Config

### Dependency

Testing roles may rely upon additional dependencies. Molecule handles managing these dependencies by invoking configurable dependency managers.  

- Ansible Galaxy
- Gilt
- Shell

Example:

```yaml
dependency:
  name: galaxy
  options:
    ignore-certs: True
    ignore-errors: True
    role-file: requirements.yml
```

### Driver

Molecule uses Ansible to manage instances to operate on. Molecule supports any provider Ansible supports. This work is offloaded to the provisioner.  
The driver’s name is specified in molecule.yml, and can be overridden on the command-line. Molecule will remember the last successful driver used, and continue to use the driver for all subsequent subcommands, or until the instances are destroyed by Molecule.

- Delegated
- Docker (default)
- Podman

Example:

```yaml
driver:
  name: docker
platforms:
  - name: instance
    hostname: instance
    image: image_name:tag
    dockerfile: Dockerfile.j2
    pull: True|False
    pre_build_image: True|False
    registry:
      url: registry.example.com
      credentials:
        username: $USERNAME
        password: $PASSWORD
        email: user@example.com
        user: root
    override_command: True|False
    command: sleep infinity
    tty: True|False
    pid_mode: host
    privileged: True|False
    security_opts:
      - seccomp=unconfined
    devices:
      - /dev/fuse:/dev/fuse:rwm
    volumes:
      - /sys/fs/cgroup:/sys/fs/cgroup:ro
    keep_volumes: True|False
    tmpfs:
      - /tmp
      - /run
    capabilities:
      - SYS_ADMIN
    sysctls:
      net.core.somaxconn: 1024
      net.ipv4.tcp_syncookies: 0
    exposed_ports:
      - 53/udp
      - 53/tcp
    published_ports:
      - 0.0.0.0:8053:53/udp
      - 0.0.0.0:8053:53/tcp
    ulimits:
      - nofile:262144:262144
    dns_servers:
      - 8.8.8.8
    etc_hosts: "{'host1.example.com': '10.3.1.5'}"
    networks:
      - name: foo
      - name: bar
    network_mode: host
    purge_networks: true
    docker_host: tcp://localhost:12376
    cacert_path: /foo/bar/ca.pem
    cert_path: /foo/bar/cert.pem
    key_path: /foo/bar/key.pem
    tls_verify: true
    env:
      FOO: bar
    restart_policy: on-failure
    restart_retries: 1
    buildargs:
        http_proxy: http://proxy.example.com:8080/
```

### Lint

Starting with v3, Molecule handles project linting by invoking and external lint commands as exemplified below.

The decision to remove the complex linting support was not easily taken as we do find it very useful. The issue was that molecule runs on scenarios and linting is usually performed at repository level.

It makes little sense to perform linting in more than one place per project. Molecule was able to use up to three linters and while it was aimed to flexible about them, it ended up creating more confusions to the users. We decided to maximize flexibility by just calling an external shell command.

Example:

```yaml
lint: |
  set -e
  yamllint .
  ansible-lint
  flake8
```

### Platforms

Platforms define the instances to be tested, and the groups to which the instances belong.

Example:

```yaml
platforms:
  - name: instance-1
    groups:
      - group1
      - group2
    children:
      - child_group1
```

### Provisioner

Molecule handles provisioning and converging the role.

- Ansible

**Important**

Ansible is the default provisioner. No other provisioner will be supported.  

Molecule’s provisioner manages the instances lifecycle. However, the user must provide the create, destroy, and converge playbooks. Molecule’s init subcommand will provide the necessary files for convenience.  

Molecule will skip tasks which are tagged with either molecule-notest or notest. With the tag molecule-idempotence-notest tasks are only skipped during the idempotence action step.

Reserve the create and destroy playbooks for provisioning. Do not attempt to gather facts or perform operations on the provisioned nodes inside these playbooks.  

Molecule will remove any options matching ‘^[v]+$’, and pass -vvv to the underlying ansible-playbook command when executing molecule –debug.  

The playbook loading order is:

- provisioner.playbooks.$driver_name.$action
- provisioner.playbooks.$action
- bundled_playbook.$driver_name.$action

**side_effect playbook**

The side effect playbook executes actions which produce side effects to the instances(s). Intended to test HA failover scenarios or the like. It is not enabled by default. Add the following to the provisioner’s playbooks section to enable.

```yaml
provisioner:
  name: ansible
  playbooks:
    side_effect: side_effect.yml
```

**prepare playbook**

The prepare playbook executes actions which bring the system to a given state prior to converge. It is executed after create, and only once for the duration of the instances life.  

```yaml
provisioner:
  name: ansible
  playbooks:
    prepare: prepare.yml
```

**cleanup playbook**

The cleanup playbook is for cleaning up test infrastructure that may not be present on the instance that will be destroyed. The primary use-case is for “cleaning up” changes that were made outside of Molecule’s test environment. For example, remote database connections or user accounts. Intended to be used in conjunction with prepare to modify external resources when required.

The cleanup step is executed directly before every destroy step. Just like the destroy step, it will be run twice. An initial clean before converge and then a clean before the last destroy step. This means that the cleanup playbook must handle failures to cleanup resources which have not been created yet.

Add the following to the provisioner’s playbooks section to enable.

```yaml
provisioner:
  name: ansible
  playbooks:
    cleanup: cleanup.yml
```

### Scenario

A scenario is a self-contained directory containing everything necessary for testing the role in a particular way. The default scenario is named default, and every role should contain a default scenario.

```yaml
scenario:
  create_sequence:
    - dependency
    - create
    - prepare
  check_sequence:
    - dependency
    - cleanup
    - destroy
    - create
    - prepare
    - converge
    - check
    - destroy
  converge_sequence:
    - dependency
    - create
    - prepare
    - converge
  destroy_sequence:
    - dependency
    - cleanup
    - destroy
  test_sequence:
    - dependency
    - lint
    - cleanup
    - destroy
    - syntax
    - create
    - prepare
    - converge
    - idempotence
    - side_effect
    - verify
    - cleanup
    - destroy
```

### Verifier

Molecule handles role testing by invoking configurable verifiers.

- Ansible (default)
- Testinfra

**Ansible**
Molecule executes a playbook (verify.yml) located in the role’s scenario.directory.

**Testinfra**
Testinfra is no longer the default test verifier since version 3.0.

## Testing

### Gitlab CI

Here is an example setting up a virtualenv and testing an Ansible role via Molecule. User-level pip is cached and so is the virtual environment to save time. And this is run over a runner tagged pip36 and docker, because its a minimal CentOS 7 VM installed with pip36 from IUS repository and docker.

```yaml
---
image: docker:latest

services:
  - docker:dind

before_script:
  - apk update && apk add --no-cache
    python3-dev py3-pip gcc git curl build-base
    autoconf automake py3-cryptography linux-headers
    musl-dev libffi-dev openssl-dev openssh
  - docker info
  - python3 --version
  - python3 -m pip install ansible molecule[docker] ansible-lint
  - ansible --version
  - molecule --version

molecule:
  stage: test
  script:
    - molecule test
```

## Source

[Molecule 2 to 3 migration script](https://gist.github.com/geerlingguy/19aace82f94b2d07a0dfb23db7345a57)
[Molecule breakable changes](https://github.com/ansible-community/molecule/issues/2560)
[Molecule Changelog](https://molecule.readthedocs.io/en/latest/changelog.html)  
[Molecule Docker images](https://quay.io/repository/ansible/molecule)  
[Molecule Driver](https://molecule.readthedocs.io/en/stable/configuration.html#driver)  
[Molecule GitHub](https://github.com/ansible/molecule)  
[Molecule Read the docs](https://molecule.readthedocs.io/en/latest/)
[TestInfra](https://testinfra.readthedocs.io/en/latest/index.html)
[Yamllint](https://yamllint.readthedocs.io/en/stable/index.html#)
