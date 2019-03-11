# Atom : Installation et Configuration

### Version des outils

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   1803  |
|           Atom           |  1.28.1 |

### Procédure d'installation

Dl + Clic + Install

### Procédure de post-installation

Installation des packages supplémentaires :

```shell
apm install atom-beautify busy-signal compare-files file-icons highlight-selected intentions language-ansible language-docker language-groovy linter linter-js-yaml linter-ui-default linter-vagrant-validate minimap minimap-highlight-selected minimap-linter minimap-split-diff sort-lines split-diff
```

### Knowledge Base

#### ATOM_HOME

Alternatively you can set the _ATOM_HOME_ environment variable to point wherever you want (you can write a .sh or .cmd script to temporarily set it and launch it from that)  

#### Proxy and firewall settings

```shell
apm config set strict-ssl false
apm config set https-proxy YOUR_PROXY_ADDRESS
```

#### Apm Install package

```shell
apm install <package_name> # to install the latest version.
apm install <package_name>@<package_version>  # to install a specific version.
```

### Cheat Sheet

#### Atom Basics

| Actions                           | Shortcuts          |
| --------------------------------- | ------------------ |
| Command Palette                   | `Ctrl+Shift+P`     |
| Settings view                     | `Ctrl+,`           |
| Opening a file                    | `Ctrl+O`           |
| Save file                         | `Ctrl+S`           |
| Open directory                    | `Ctrl+Shift+A`     |
| Open a file in a project          | `Ctrl+T or Ctrl+P` |
| Open a file in a project recently | `Ctrl+B`           |

#### Moving in Atom

| Actions                                         | Shortcuts     |
| ----------------------------------------------- | ------------- |
| Navigate with symbol                            | `Ctrl+R`      |
| Bookmarks line                                  | `Alt+Ctrl+F2` |
| Next Bookmarks                                  | `F2`          |
| Previous Bookmarks                              | `Shift+F2`    |
| Open Bookmarks                                  | `Ctrl+F2`     |
| Move to the beginning of word                   | `Ctrl+Left`   |
| Move to the end of word                         | `Ctrl+Right`  |
| Move to the first character of the current line | `Home`        |
| Move to the end of the line                     | `End`         |
| Move to the top of the file                     | `Ctrl+Home`   |
| Move to the bottom of the file                  | `Ctrl+End`    |
| Move directly                                   | `Ctrl+G`      |

#### Editing and Deleting Text

| Actions                                                                              | Shortcuts          |
| ------------------------------------------------------------------------------------ | ------------------ |
| Upper case the current word                                                          | `Ctrl+K Ctrl+U`    |
| Lower case the current word                                                          | `Ctrl+K Ctrl+L`    |
| Delete current line                                                                  | `Ctrl+Shift+K`     |
| Delete to beginning of word                                                          | `Ctrl+Backspace`   |
| Delete to end of word                                                                | `Ctrl+Delete`      |
| Add a new cursor at the clicked location                                             | `Ctrl+Click`       |
| Add another cursor above/below the current cursor                                    | `Alt+Ctrl+Up/Down` |
| Select the next word in the document that is the same as the currently selected word | `Ctrl+D`           |
| Select all words in the document that are the same as the currently selected word    | `Alt+F3`           |
| Jump to the bracket matching the one adjacent to the cursor.                         | `Ctrl+M`           |
| Select all the text inside the current brackets                                      | `Alt+Ctrl+,`       |
| Close the current XML/HTML tag                                                       | `Alt+Ctrl+.`       |

#### Find and Replace

| Actions                   | Shortcuts      |
| ------------------------- | -------------- |
| Search within a buffer    | `Ctrl+F`       |
| Search the entire project | `Ctrl+Shift+F` |

#### Panes

| Actions    | Shortcuts                        |
| ---------- | -------------------------------- |
| Split Pane | `Ctrl+K Up/Down/Left/Right`      |
| Move Pane  | `Ctrl+K Ctrl+Up/Down/Left/Right` |
| Close Pane | `Ctrl+K Ctrl+W`                  |

#### Grammar

| Actions        | Shortcuts      |
| -------------- | -------------- |
| Select grammar | `Ctrl+Shift+L` |

#### Snippets

| Actions       | Shortcuts      |
| ------------- | -------------- |
| Show Snippets | `Ctrl+Shift+P` |

### Source

[Atom Flight Manual](https://flight-manual.atom.io/)
