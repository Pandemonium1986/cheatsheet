# Commit Best Practice

## Tools versions

|  Os / Tool | Version |
| :--------: | :-----: |
| Linux Mint |   19.3  |
| pre-commit |  2.8.2  |
|   gitlint  |  0.14.0 |

## Todo

N/A

## Bulk Note

N/A

## About

**Pre-commit**: A framework for managing and maintaining multi-language pre-commit hooks.  
**Git-lint**: Git commit message linter.

## Installation procedure

#### Pre-commit

```sh
pip install --user --upgrade pre-commit
```

#### Git-lint

```sh
pip install --user --upgrade gitlint
```

## Getting start

#### Pre-commit

Add a pre-commit configuration

```sh
cd MY_REPO && \
touch .pre-commit-config.yaml && \
pre-commit sample-config > .pre-commit-config.yaml
```

Install the git hook scripts

```sh
cd MY_REPO && \
pre-commit install
```

Run against all the files (first execution)

```sh
pre-commit run --all-files
```

How does it work  
pre-commit is configured via the .pre-commit-config.yaml file.  
The configuration file is divided into three levels :

-   Top level (see [here](https://pre-commit.com/#pre-commit-configyaml---top-level)).
    -   repos (see [here](https://pre-commit.com/#pre-commit-configyaml---repos)).
        -   hooks(see [here](https://pre-commit.com/#pre-commit-configyaml---hooks)).

Repos should be a git url to clone.  
Hooks represent the "action" to perfom.  
A repository can contain many hooks.

**Advanced Feature**  
You can execute hooks from local scripts and/or local cli (see [here](https://pre-commit.com/#repository-local-hooks)).
In my case cli must be installed before running pre-commit hooks.

```sh
pip install --user --upgrade ansible-lint yamllint && \
sudo npm install -g eclint && \
sudo curl -L https://github.com/hadolint/hadolint/releases/download/v1.18.2/hadolint-Linux-x86_64 --output /usr/local/bin/hadolint && \
sudo chmod 755 /usr/local/bin/hadolint
```

This allows pre-commit to use certain linter with the configuration files located at the root of the projects.

#### Git-lint

Add a gitlint configuration

```sh
cd MY_REPO && \
gitlint generate-config
```

Linting a range of commits

```sh
gitlint --commits "019cf40...d6bc75a"
```

## Source

[Docs: convetional commit](https://www.conventionalcommits.org/fr/v1.0.0/)
[Docs: gitlint](https://github.com/jorisroovers/gitlint)
[Docs: pre-commit](https://pre-commit.com)
[GitHub: gitlint](https://github.com/jorisroovers/gitlint)
