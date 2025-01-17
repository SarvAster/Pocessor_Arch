Répertoire qui contient le démarrage du TP sur la réalisation du processeur riscv.

Récupérer le projet
---------------------
Faire un clone pour récupérer le projet.

`git clone git@gitlab-student.centralesupelec.fr:comparch/processeur.git`

Les fichiers du TP se trouvent normalement dans le répertoire `processeur` : `cd processeur`

Makefiles
---------


### Simuler

Test de l'instruction lui :

`cd implem && make simulation PROG=lui `

### Synthétiser

Test des leds sur carte : 

`cd implem && make fpga PROG=test_led_x31`

Space Invader sur carte :

`cd implem && make fpga PROG=invader LIB=libfemto`

### Autres

`cd implem && make help`


Installation sur votre propre ordinateur
----------------------------------------

## Dépendances

Nous fournissons un [script d'installation](https://gitlab-student.centralesupelec.fr/comparch/processeur/-/blob/master/install.sh) automatique pour Debian qui installe Vivado, la chaîne de compilation RISC-V et les dépendances. Si vous voulez installer manuellement, il vous faudra :
* *Vivado* -> La version minimale *19.1 WebPAck Edition* est requise pour faire fonctionner le contrôleur HDMI ([Téléchargement de Vivado](https://www.xilinx.com/support/download.html))
* *Toolchain gcc-riscv* -> Le plus simple est d'installer le paquet adéquat (par exemple, sous Debian `sudo apt install gcc-riscv-unknown-elf`). Elle peut aussi être compilée et installée à l'aide du [dépôt Outils](https://gricad-gitlab.univ-grenoble-alpes.fr/riscv-ens/outils)

## Environnement

Pour pouvoir utiliser les Makefiles du projet afin de simuler/synthetiser les modèles matériels VHDL et de compiler les programes de test et applications, il faut faire connaître à son environnement de travail les chemins vers les outils utilisés :

* Si vous avez installé la chaîne de compilation en clonant le dépôt outil (cette étape n'est pas nécessaire si vous avez installé la chaîne de compilation via un paquet), ajout du chemin vers la chaîne de compilation dans le PATH:

`export PATH=${PATH}:/opt/riscv-cep-tools/bin`

Remplacer */opt/riscv-cep-tools* par le chemin où votre chaîne
de compilation RISC-V est installée sur votre machine

* Ajout des chemins vers les outils Vivado: 

`source /opt/Xilinx/Vivado/2019.1/settings64.sh` 

Remplacer éventuellement */opt/* par le chemin où Vivado est installé sur votre machine
