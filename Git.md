# Git : Installation et Configuration

### Version des outils
Os / Tool | Version
:---: | :---:
Windows 10 Professionnel | 1709
Git For Windows | 2.16.2.windows.1

### Procédure d'installation

La procédure d'installation de _Git for Windows_ sur _Windows 10_ se déroule de la façon suivante :

Commencez par exécuter l'installeur _Git-2.16.2-64-bit.exe_.  

Dans la fenêtre _Information_ cliquez sur **_Next_**  
![Information](/img/git-001.png)  

Dans la fenêtre _Select Destination Location_ laissez par défault et cliquez sur **_Next_**  
![Select Destination Location](/img/git-002.png)  

Dans la fenêtre _Select Components_ on choisira **de ne pas associer** les fichiers .sh pour ne pas interférer avec le bash Ubuntu. On veillera aussi à ce que les mises à jour soient vérifiées quotidiennement. Après avoir coché/décoché les checkbox en question, cliquez sur  **_Next_**  
![Select Components](/img/git-003.png)  

Dans la fenêtre _Select Start Menu Folder_ laissez par défault et cliquez sur **_Next_**  
![Select Start Menu Folder](/img/git-004.png)  

Dans la fenêtre _Choosing the default editor used by Git_ on continuera d'utiliser _vim_ du fait d'une mauvaise intégration de _Notepad++_ en cas d'installation personnalisée. Après avoir choisit _Vim_, cliquez sur  **_Next_**  
![Choosing the default editor used by Git](/img/git-005.png)  

Dans la fenêtre _Adjusting your Path environment_ laissez par défault et cliquez sur **_Next_**  
![Adjusting your Path environment](/img/git-006.png)  

Dans la fenêtre _Choosing HTTPS transport backend_ laissez par défault et cliquez sur **_Next_**  
![Choosing HTTPS transport backend](/img/git-007.png)  

Dans la fenêtre _Configuring the line ending conversions_ choisissez la deuxième optionset cliquez sur **_Next_**  
![Configuring the line ending conversions](/img/git-008.png)  

Dans la fenêtre _Configuring the terminal emulator to use with Git Bash_ laissez par défault et cliquez sur **_Next_**  
![Configuring the terminal emulator to use with Git Bash](/img/git-009.png)  

Dans la fenêtre _Configuring extra options_ laissez par défault et cliquez sur **_Next_**  
![Configuring extra options](/img/git-010.png)  

### Procédure de configuration
La procédure de confiuguration de _Git for Windows_ sur _Windows 10_ se déroule de la façon suivante :  

Commencez par éxécuter les deux commandes suivantes :
```java
git config --global user.email "prenom.nom@gmail.com"
git config --global user.name "GitHub account name"
```

Editez ensuite le fichier ~/.gitconfig avec le fichier [gitconfig](./gitconfig)
