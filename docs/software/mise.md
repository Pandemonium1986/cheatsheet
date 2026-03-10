# Mise (Mise en place)

## TL;DR

## About

> `mise` (pronounced "meez") or "mise-en-place" is a development environment setup tool. The name refers to a French culinary phrase that roughly translates to "setup" or "put in place". The idea is that before one begins cooking, they should have all their utensils and ingredients ready to go in their place.
>
> `mise` does the same for your projects. Using its `mise.toml` config file, you'll have a consistent way to setup and interact with your projects no matter what language they're written in.  
> Its functionality is grouped into 3 categories described below.
>
> `mise` installs and manages dev tools/runtimes like node, python, or terraform both simplifying installing these tools and allowing you to specify which version of these tools to use in different projects. `mise` supports _hundreds_ of dev tools.
>
> `mise` manages environment variables letting you specify configuration like `AWS_ACCESS_KEY_ID` that may differ between projects. It can also be used to automatically activate a _Python virtualenv_ when entering projects too.
>
> `mise` is a task runner that can be used to share common tasks within a project among developers and make things like running tasks on file changes easy.

## Tools versions

| Os / Tool |  Version  |
| :-------- | :-------: |
| Sles      |   15sp7   |
| Mise      | 2026.2.19 |

## Todo

- N/A

## Installation

### Curl

```sh
curl https://mise.run | MISE_INSTALL_PATH=/usr/local/bin/mise sh
```

### Zypper

```sh
zypper addrepo --repo https://mise.jdx.dev/rpm/mise.repo && \
zypper --gpg-auto-import-keys --non-interactive refresh --repo mise-repo
zypper --non-interactive install --no-recommends mise
```

## Getting start

### Mise exec

Once `mise` is installed, you can immediately start using it. `mise` can be used to install and run tools, launch tasks, and manage environment variables.

The most essential feature `mise` provides is the ability to run tools with specific versions. A simple way to run a shell command with a given tool is to use `mise x|exec`. For example, here is how you can start a Python 3 interactive shell (REPL):

```sh
mise exec python@3 -- python
```

### Mise run

Another useful command is `mise r|run` which allows you to run a `mise` task or a script with the `mise` context.

## Walkthrough

### Installing Dev Tools

The main command for working with tools in mise is `mise u|use`. This does 2 main things:

- Installs tools (if not already installed)
- Adds the tool to the `mise.toml` configuration file—in mise I say the tool is "active" if it's in `mise.toml`

### Dev Tool Backends

Tools are installed with a variety of backends like `asdf`, `github`, or `vfox`. See registry for the full list of shorthands like `node` you can use.  
You can also use other backends like `npm` or `cargo` which can install any package from their respective registries:

```sh
mise use npm:@antfu/ni
mise use cargo:starship
```

### Setting Environment Variables

`mise` can also be used to set environment variables for your project. You can set environment variables with the CLI:

```sh
mise set MY_VAR=123
echo $MY_VAR
# 123
```

### Tasks

Tasks are defined in a project to execute commands.  
You can define tasks in a `mise.toml`:

```toml
[tasks]
build = "npm run build"
test = "npm test"
```

### Common Commands

Since there are a lot of commands available in mise, here are what I consider the most important:

- `mise completion` – Set up completions for your shell.
- `mise cfg|config` – A bunch of commands for working with mise.toml files via the CLI.
- `mise x|exec` – Execute a command in the mise environment without activating mise.
- `mise g|generate` – Generates things like Git hooks, task documentation, GitHub Actions, and more for your project.
- `mise i|install` – Install tools.
- `mise link` – Symlink a tool installed by some other means into the mise.
- `mise ls-remote` – List all available versions of a tool.
- `mise ls` – Lists information about installed/active tools.
- `mise outdated` – Informs you of any tools with newer versions available.
- `mise plugin` – Plugins can extend mise with new functionality like extra tools or environment variable management. Commonly, these are simply asdf plugins or modern plugins.
- `mise r|run` – Run a task defined in mise.toml or mise-tasks.
- `mise self-update` – Update mise to the latest version. Don't use this if you installed mise via a package manager.
- `mise settings` – CLI access to get/set configuration settings.
- `mise rm|uninstall` – Uninstall a tool.
- `mise up|upgrade` – Upgrade tool versions.
- `mise u|use` – Install and activate tools.
- `mise w|watch` – Watch for changes in a project and run tasks when they occur.

## Configuration

`mise.toml` is the config file for `mise`. They can be at any of the following file paths (in order of precedence, top overrides configuration of lower paths):

- `mise.local.toml` - used for local config, this should not be committed to source control
- `mise.toml`
- `mise/config.toml`
- `.mise/config.toml`
- `.config/mise.toml` - use this in order to group config files into a common directory
- `.config/mise/config.toml`
- `.config/mise/conf.d/*.toml` - all files in this directory will be loaded in alphabetical order

### Target File for Write Operations

When commands like `mise use`, `mise set`, or `mise unuse` need to write to a config file, they use the lowest precedence file in the highest precedence directory.

### Sections

- [tools] - Dev tools
- [env] - Arbitrary Environment Variables
- [tasks.*] - Run files or shell scripts
- [settings] - Mise Settings
- [plugins] - Specify Custom Plugin Repository URLs
- [tool_alias] - Tool version aliases
- [shell_alias] - Shell aliases

### Environments

> Normally environment variables in mise are used to set settings so most environment variables are in that doc. The following are environment variables that are not settings.  
> A setting in mise is generally something that can be configured either as an environment variable or set in a config file.

- MISE_DATA_DIR
- MISE_CACHE_DIR
- MISE_TMP_DIR
- MISE_SYSTEM_DIR
- MISE_GLOBAL_CONFIG_FILE
- MISE_GLOBAL_CONFIG_ROOT
- MISE_ENV_FILE
- MISE\_${PLUGIN}\_VERSION
- MISE_TRUSTED_CONFIG_PATHS
- MISE_CEILING_PATHS
- MISE_LOG_LEVEL=trace|debug|info|warn|error
- MISE_LOG_FILE=~/mise.log
- MISE_LOG_FILE_LEVEL=trace|debug|info|warn|error
- MISE_LOG_HTTP=1
- MISE_QUIET=1
- MISE_HTTP_TIMEOUT
- MISE_RAW=1
- MISE_FISH_AUTO_ACTIVATE

## Settings

Numerous settings are available. See the [settings](https://mise.jdx.dev/configuration/settings.html) page for a complete list.

Some interresting settings :

- cache_prune_age
- ceiling_paths
- color
- color_theme
- experimental
- github_attestations
- gpg_verify
- locked
- lockfile
- netrc
- netrc_file
- offline
- os
- paranoid
- terminal_progress
- trusted_config_paths
- use_versions_host_track
- verbose
- yes

## Dev Tools

`mise` is a tool that manages installations of programming language runtimes and other tools for local development. For example, it can be used to manage multiple versions of Node.js, Python, Ruby, Go, etc. on the same machine.

### Tool Resolution Flow

When you enter a directory or run a command, mise follows this process:

- Configuration Discovery: mise walks up the directory tree looking for configuration files (mise.toml, .tool-versions, etc.) and merges them hierarchically
- Tool Resolution: mise resolves version specifications (like node@latest or python@3) to specific versions using registries and version lists
- Backend Selection: mise chooses the appropriate backend to handle each tool (core, asdf, aqua, etc.)
- Installation Check: mise verifies if the required tool versions are installed, automatically installing missing ones
- Environment Setup: mise configures your PATH and environment variables to use the resolved tool versions

### Environment Integration

`mise` provides several ways to integrate with your development environment:

- Automatic Activation with `mise activate`.
- On-Demand Execution with `mise exec`.
- Shims: `mise` can create lightweight wrapper scripts that automatically use the correct tool.

### OS-Specific Tools

You can restrict tools to specific operating systems using the `os` field

```toml
[tools]
ripgrep = { version = "latest", os = ["linux", "macos"] }
```

### Common commands

#### mise use

For some users, `mise use` might be the only command you need to learn. It will do the following:

- Install the tool's plugin if needed
- Install the specified version
- Set the version as active (i.e. update the PATH)
- Update the current configuration file (mise.toml or .tool-versions)

#### mise install

`mise install` will install but not activate tools—meaning it will download/build/compile the tool into `~/.local/share/mise/installs` but you won't be able to use it without "setting" the version in a `.mise-toml` file.

#### mise exec|mise x

`mise x` can be used for one-off commands using specific tools. e.g.: if you want to run a script with python3.12:

```sh
mise x python@3.12 -- ./myscript.py
```

## Shims

When using shims, `mise` places small executables (`shims`) in a directory that is included in your `PATH`. You can think of `shims` as symlinks to the mise binary that intercept commands and load the appropriate context.

## mise.lock Lockfile

`mise.lock` is a lockfile that pins exact versions and checksums of tools for reproducible environments. When enabled, mise will automatically maintain this file to ensure consistent tool versions across different machines and deployments.

## Prepare (experimental)

The `mise prepare` command ensures project dependencies are ready by checking if lockfiles are newer than installed outputs (e.g., `package-lock.json` vs `node_modules/`) and running install commands if needed.

## Backend Architecture

Backends are mise's way of supporting different tool installation methods. Each backend knows how to:

- List available versions of tools
- Download and install specific versions
- Set up the environment for installed tools
- Manage tool lifecycles (updates, uninstalls)

Think of backends as "adapters" that let mise work with different package managers and installation systems.

## Environments

Environment variables are available when using `mise x|exec`, or with `mise r|run` (i.e. with tasks):

```sh
mise set MY_VAR=123
mise exec -- echo $MY_VAR
```

## Secret

Use mise to manage sensitive environment variables securely. There are multiple supported approaches:

- `fnox` recommended — Full-featured secret manager with remote secret storage (e.g.: 1Password, AWS Secrets Manager) and remote encryption (e.g.: AWS KMS). This is a separate project by @jdx that works well alongside mise. There's no direct integration with mise and fnox, you set it up separately.
- `sops` experimental — Encrypt entire files and load them via `env._.file`
- `Direct age encryption` experimental — Encrypt individual env vars inline in `mise.toml`

### Direct age Encryption

Encrypt individual environment variable values directly in `mise.toml` using `age` encryption. The `age` tool is not required—mise has support built-in.

This is a simple method of storing encrypted environment variables directly in `mise.toml`. You can use it simply by running `mise set --age-encrypt <key>=<value>`. By default, mise will use your SSH key (`~/.ssh/id_ed25519` or `~/.ssh/id_rsa`) if it exists.

- Inline storage: values live alongside other env vars in mise.toml
- Multiple recipients: x25519 age keys and SSH recipients
- Automatic decryption: at runtime when identities are available

### Hooks

You can have mise automatically execute scripts during a `mise activate` session. You cannot use these without the `mise activate` shell hook installed in your shell—except the `preinstall` and `postinstall` hooks. The configuration goes into `mise.toml`.

Here is the list of available hooks:

- CD hook
- Enter hook
- Leave hook
- Preinstall/postinstall hook
- Tool-level postinstall
- Task hooks
- Watch files hook
- Hook execution
- Shell hooks
- Multiple hooks syntax

## Tasks

> Like `make` it manages tasks used to build and test projects.

You can define tasks in `mise.toml` files or as standalone shell scripts. These are useful for things like running linters, tests, builders, servers, and other tasks that are specific to a project. Of course, tasks launched with mise will include the mise environment—your tools and env vars defined in `mise.toml`.

### Tasks in mise.toml files

```toml
[tasks.build]
description = "Build the CLI"
run = "cargo build"
```

### Tasks in file

```sh
vim mise-tasks/build
```

```sh
#!/usr/bin/env bash
#MISE description="Build the CLI"
cargo build
```

### Tasks dependencies

`mise` supports three types of task dependencies:

- depends - Prerequisites - Tasks that must complete successfully before this task runs.
- depends_post - Cleanup Tasks - Tasks that run after this task completes (whether successful or failed).
- wait_for - Soft Dependencies - Tasks that should run first if they're in the current execution, but don't fail if they're not available.

### Tasks advanced features

- Conditional Dependencies.
- Dynamic Dependencies.
- Cross-Project Dependencies.
- Source and Output Tracking.
- Incremental Execution.
- Parallel File Watching.

## Tip

### Edit tip

Use `mise edit` to open an interactive editor for your configuration. It provides a TUI where you can navigate sections, add tools from the registry with fuzzy search, and configure settings with schema-aware autocompletion.

### Config tip

Use `mise config ls` to see the configuration files currently used by `mise`.

### Tasks tip

`mise run` sets up the "mise environment" before running the task (tools and environment variables). So if you'd rather not activate mise in your shell, you can use mise run to run tasks, and it will have the tools in PATH and the environment variables from mise.toml set.

## Source

[Mise](https://mise.jdx.dev/)  
[Mise-version](https://mise-versions.jdx.dev/)
[When to Use Each Backend](https://mise.jdx.dev/dev-tools/backend_architecture.html#when-to-use-each-backend)
