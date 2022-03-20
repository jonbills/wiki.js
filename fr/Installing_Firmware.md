---
title: installation firmware
description: 
published: true
date: 2020-10-19T00:45:52.362Z
tags: 
editor: undefined
dateCreated: 2020-10-16T22:01:54.254Z
---

# Chargement du micrologiciel Speeduino
## Survol
Le micrologiciel Speeduino est le code qui fait fonctionner le module et doit être installé sur votre module avant de pouvoir utiliser le ECU. De nouvelles version du micrologiciel sont lancées régulièrement (aux deux mois environ) et ils permettent de nouvelles fonctionnalités, des corrections de bugs et des améliorations de performances. Donc il est recommandé de rester à jour pour les micro logiciels.  

Voulant garder un maximum de simplicité, le processus de compilation et d'installation du micrologiciel est raisonnablement simple. La plupart des utilisateurs utiliseront la méthode 'SpeedyLoader' pour l'installation du micrologiciel.


## Installation - SpeedyLoader

La méthode la plus simple (et recommandée) d'installer le micrologiciel Speeduino sur un Arduino standard MEGA 2560 est avec l'utilitaire SpeedyLoader. SpeedyLoader fera lui-même le transfert du micrologiciel et de l'installation de celui-ci sans aucune nécessité de compilation manuelle. Vous pouvez choisir lea version la plus récente ou sélectionner une des versions plus ancienne si vous le préférez. SpeedyLoader téléchargera le fichier INI et si désiré un fichier de programmation de base qui sera possible de charger dans le logiciel TunerStudio.

-   **Windows:** [32-bit](https://github.com/speeduino/SpeedyLoader/releases/latest/download/SpeedyLoader-ia32.exe) / [64-bit](https://github.com/speeduino/SpeedyLoader/releases/latest/download/SpeedyLoader-x64.exe)
-   **Mac:** [SpeedyLoader.dmg](https://github.com/speeduino/SpeedyLoader/releases/latest/download/SpeedyLoader.dmg)
-   **Linux:** [SpeedyLoader.AppImage](https://github.com/speeduino/SpeedyLoader/releases/latest/download/SpeedyLoader.AppImage) (Doit être exécuté après le téléchargement)
    -   Linux requiert que la bibliothèque libusb soit installée. exemple :  si sur Debian/Ubuntu:
            `sudo apt-get install libusb-1.0-0 libusb-0.1-4:i386`
-   **Raspberry Pi** [SpeedyLoader.AppImage](https://github.com/speeduino/SpeedyLoader/releases/latest/download/SpeedyLoader-armv7l.AppImage)
    -   Raspberry Pi / Utilisateurs Raspbian peuvent installer la bibliothèque de cette façon:
            `sudo apt-get install libusb-1.0-0 libusb-0.1-4`

Une fois le micrologiciel installé sur la plaque, voir  [Se connecter à TunerStudio](/Connecting_to_TunerStudio) pour plus de détails sur comment configurer TunerStudio

## Installation - Compilation manuelle
> Note: la compilation manuelle du micrologiciel **n'est pas** nécessaire pour installer Speeduino, la façon la plus simple (et recommandée pour la plupart des usagers) est d'utiliser SpeedyLoader tel que décrite ci-haut.
{.is-warning}

 
Si vous voulez complier le micrologiciel vous-même, ou de faire des changement dans le code, les codes sources sont disponibles gratuitement.

### Requis

-   un PC Windows, Mac ou linux 
-   un parmi les choix suivants:
    -   [Le Arduino IDE](http://arduino.cc/en/Main/Software). La version la plus vieille supportée est la 1.6.7, mais il est recommandé d'utiliser la version la plus à jour.
    -   [PlatformIO](http://platformio.org/). Disponible pour téléchargement ici: <http://platformio.org/platformio-ide>
-   Une copie du code source Speeduino le plus récent. Voir plus bas.
-   Une copie de [TunerStudio](http://www.tunerstudio.com/index.php/downloads) pour tester que le micrologiciel a été chargé correctement.

### Téléchargement du micrologiciel

Il y a deux méthodes pour obtenir le micrologiciel Speeduino:

1.  Des versions régulières et stables sont produites et relâchées sur Github. On peut les retrouver ici: <https://github.com/noisymime/speeduino/releases>
2.  Si vous voulez les versions les plus récentes et avec plus donc fonctionnalités, (quelque fois non parfaites et ou non stables) elles sont disponibles ici: <https://github.com/noisymime/speeduino>

### Compilation du micrologiciel

-   Démarrez le IDE, sélectionnez *Fichier &gt; ouvrir*, naviguez à l'emplacement où vous avez téléchargé le Speeduino et ouvrez le fichier **speeduino.ino**.
-   Sélectionnez le type de plaque: *Outils &gt; Type de carte &gt; Arduino Mega 2560* ou Mega ADK (Ce sont les deux seuls types supportés présentement)
-   Cliquez l'icône **Vérifier** dans le coin gauche en haut (ressemble à un crochet)

À ce point vous devriez avoir compilé le micrologiciel! Si vous rencontrez des problèmes voir le guide de dépannage : [dépannage](http://speeduino.com/wiki/index.php?title=Compiling_and_Installing_Firmware&action=edit&section=4#Troubleshooting) plus bas. (Anglais seulement pour l'instant)

Le video démontre la marche a suivre complète de l'installation du micro logiciel sur le arduino à partir de zéro:

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/AX9URou4JTs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

#### Optionnel (Mais recommandé)

Il existe une option de changer le niveau d'optimisation dans le 'compiler'. Par défaut, le IDE utilise le '-0s' comme option, ce qui focus à faire de plus petits fichiers. Étant donné que la grosseur des fichiers n'est pas un problèmes mais que la vitesse est à considérer, changer l'option a '-03' produit de meilleurs résultats. (20% plus rapide mais avec des fichiers 40% plus gars approx.) Pour faire cela, vous devez éditer le fichier platform.txt :

-   Le Arduino IDE ne doit pas être en fonction
-   Ouvrir le fichier platform.txt qui est dans ces endroits:
    -   Sur Windows: c:\\Program Files\\Arduino\\hardware\\arduino\\avr
    -   Sur Mac: /Applications/Arduino/Contents/Resources/Java/hardware/arduino/avr/
    -   Sur Linux:
-   Pour les 3 entrées suivantes, changez les 'Os' pour des 'O3':
    -   compiler.c.flags
    -   compiler.c.elf.flags
    -   compiler.cpp.flags
-   Sauvegardez le fichier et redémarrez le Arduino IDE

**Note:** Ceci n'est pas ncessaire si vous utilisez 'PlatformIO', l'optimisation est automatiquement appliquée.

### Installation

Une fois que vous avez réussi, le reste est très simple.

-   Branchez le Mega 2560 dans un port USB libre.
-   Si vous avez une vieille version de **Windows** et que c'est la première fois que vous utilisez Arduino, vous devrez possiblement installer les pilotes pour les module série Arduino. (USB-UART ou "USB adapter chip").


* **ATMega16U** - Ce jeu de puce est carré près du connecteur USB - Les pilotes sont inclus pour Windows 7+, MacOS et Linux.
* **WCH CH340G** - Ce jeu de puce est rectangulaire près du connecteur USB - il utilise le pilote "CH341" dispoible : [ici](http://www.wch.cn/downloads/file/65.html) pour Windows
  * WCH-original CH340/CH341 Les pilotes pour les autres systèmes (Mac, Linux, Android, etc) peuvent être téléchargés [ici](http://www.wch.cn/downloads/CH341SER_ZIP.html).

-   Dans le Arduino IDE; selectionnez le Mega2560: *Outils &gt; type de carte*
-   Choisissez votre port série : *Outils &gt; Ports*
-   Cliquez le boutton *Upload* dans le coin supérieur gauche

### Relâches des vieux micrologiciels

Si requis les vieilles versions se retrouvent ici:[Firmware History](Firmware_History "wikilink")

### Verification du mcrologiciel 

Le micrologiciel étant maintenant installé vous pouvez maintenant passer à: [Connecter à TunerStudio](Connecting_to_TunerStudio "wikilink").

Si voulu, il est possible de faire une validation manuelle du micrologiciel en utilisant le moniteur série du Arduino IDE. Ceci peut être démarré en sélectionnant le 'Moniteur série' à partir du menu Outils.

Dans la fenêtre qui s'ouvre, tappez la lettre 'S' (en majuscule, mais sans les guillemets) et appuyez sur *enter* Le Arduino devrait répondre avec la date du code installé (xxxx.xx):

    Speeduino 2017.03

**NOTE**: S'assurer que la vitesse est de 115200 baud. 

Il est aussi possible d'enter "?" pour une liste de requêtes possible du MEGA.

### Dépannage

#### Mauvais Type d'Arduino 
Si vous voyez ceci (ou erreurs similaires) quand vous tentez de complier le micrologiciel:

    scheduler.ino:317:7: error: ‘OCR4A’ was not declared in this scope
    scheduler.ino:323:8: error: ‘TIMSK5’ was not declared in this scope
    scheduler.ino:323:25: error: ‘OCIE4A’ was not declared in this scope

Il se peut que vous ayez choisit le mauvais type de plaque Arduino. Choisissez le type en allant à:  *Outils &gt; Type de carte &gt; Arduino Mega 2560* ou Mega ADK

#### Projet complet Speeduino n'est pas ouvert

Ce qui suit peut survenir si vous ouvrez seulement le fichier speeduino.ino plutôt que le projet en entier:

`speeduino.ino:27:21: fatal error: globals.h: No such file or directory`

Assurez vous que tous les fichiers sont contenus dans le même répertoire, ensuite choisissez Fichier-&gt;Ouvrir et trouvez le fichier 'speeduino.ino'. Si vous avez ouvert le projet correctemet, vous devriez avoir plusieurs onglets dans le haut:

![speeduinoIDE.png](/img/TunerStudio/speeduinoIDE.png){.align-center width=500}

Si vous voyez seulement un fichier ou un petit nombre de fichiers; vous n'avez pas ouvert le projet en entier...