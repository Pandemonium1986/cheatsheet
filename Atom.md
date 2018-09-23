# Atom : Installation et Configuration

### Version des outils

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   1803  |
|           Atom           |  1.28.1 |

### Procédure d'installation

Dl + Clic + Install

### Procédure de post-installation

Todo

### Cheat Sheet

Alternatively you can set the ATOM_HOME environment variable to point wherever you want (you can write a .sh or .cmd script to temporarily set it and launch it from that)   

Proxy and Firewall Settings

```shell
apm config set strict-ssl false
apm config set https-proxy YOUR_PROXY_ADDRESS
```

Command Palette `Ctrl+Shift+P`  
Settings view `Ctrl+,`  
Opening a file `Ctrl+O`  
Save file `Ctrl+S`  
Open directory `Ctrl+Shift+A`  
Open a file in a project `Ctrl+T or Ctrl+P`  
Open a file in a project recently `Ctrl+B`  
Navigate withe symbol `Ctrl+R`  
Bookmarks line : `Alt+Ctrl+F2`  
Next Bookmarks : `F2`  
Previous Bookmarks : `Shift+F2`  
Open Bookmarks : `Ctrl+F2`  
`Ctrl+Shift+End` - Select to bottom of file  
`Ctrl+K Ctrl+U` - Upper case the current word  
`Ctrl+K Ctrl+L` - Lower case the current word  
`Ctrl+Shift+K` - Delete current line  

Panes :
`Ctrl+K Up/Down/Left/Right` : Split Pane.
`Ctrl+K Ctrl+Up/Down/Left/Right` : Move Pane
`Ctrl+K Ctrl+W` : Close Pane

Grammar :
`Ctrl+Shift+L` - Select grammar

`Ctrl+Click` - Add a new cursor at the clicked location  
`Alt+Ctrl+Up/Down` - Add another cursor above/below the current cursor  
`Ctrl+D` - Select the next word in the document that is the same as the currently selected word  
`Alt+F3` - Select all words in the document that are the same as the currently selected word

`Ctrl+M` - Jump to the bracket matching the one adjacent to the cursor. It jumps to the nearest enclosing bracket when there's no adjacent bracket.
`Alt+Ctrl+,` - Select all the text inside the current brackets
`Alt+Ctrl+.` - Close the current XML/HTML tag

`Ctrl+F` - Search within a buffer
`Ctrl+Shift+F` - Search the entire project

`Ctrl+Shift+P ==> Snippets: Availabla` - Show Snippets

Apm Install package

-   `apm install <package_name>` to install the latest version.
-   `apm install <package_name>@<package_version>` to install a specific version.

Move to the beginning of word `Ctrl+Left`  
Move to the end of word `Ctrl+Right`  
Move to the first character of the current line `Home`  
Move to the end of the line `End`  
Move to the top of the file `Ctrl+Home`  
Move to the bottom of the file `Ctrl+End`
Move directly `Ctrl+G`  

### Source

[Atom Flight Manual](https://flight-manual.atom.io/)
