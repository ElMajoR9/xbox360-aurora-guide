# Glossaire

Tous les termes techniques de la scène Xbox 360 homebrew expliqués simplement.

---

## A

**Aurora Dashboard**
: Interface graphique alternative au dashboard officiel Microsoft (NXE), utilisée sur les consoles JTAG/RGH. Permet de lancer des jeux, gérer des plugins, personnaliser l'interface et accéder à la console via le réseau.

**Aurora 0.7b.2**
: Dernière version publique stable d'Aurora Dashboard (au moment de la rédaction de ce guide).

---

## C

**CB (Coldboot)**
: Premier code exécuté au démarrage d'une Xbox 360. Son numéro de version est central dans les méthodes de modification (notamment le JTAG).

**CPU Key**
: Clé unique propre à chaque console Xbox 360, générée lors de la fabrication. Nécessaire pour certaines opérations avancées (backup NAND, KV, etc.). Ne doit jamais être partagée publiquement.

---

## D

**DashLaunch**
: Utilitaire système qui se charge avant le dashboard. Permet de définir le dashboard de démarrage, d'activer le FTP, de patcher le comportement système et de bloquer les connexions vers Microsoft. Indispensable sur toute console JTAG/RGH.

**Default.xex**
: Fichier exécutable principal d'un jeu ou d'une application Xbox 360. Aurora s'en sert pour détecter et lancer les jeux de la bibliothèque.

**DLC (Downloadable Content)**
: Contenu téléchargeable pour un jeu. Sur Xbox 360, les DLC sont des fichiers stockés dans `/Content/`.

---

## F

**Freestyle Dash (F3)**
: Dashboard alternatif à Aurora, souvent associé au plugin de navigation de fichiers du même nom. Moins utilisé que Aurora mais encore présent dans certaines configurations.

**FTP (File Transfer Protocol)**
: Protocole permettant de transférer des fichiers entre la console et un PC via le réseau local. C'est le principal moyen de gérer les fichiers d'une Xbox 360 modifiée depuis un ordinateur.

---

## G

**GOD (Games on Demand)**
: Format de jeu Xbox 360 téléchargé depuis le Xbox Live Marketplace. Structure de fichiers spécifique, différente des ISO.

---

## J

**JTAG**
: Première méthode de modification matérielle de la Xbox 360, exploitant l'interface JTAG du processeur. Ne fonctionne que sur les kernels ≤ 7371. Aujourd'hui remplacée par le RGH sur les consoles plus récentes.

---

## K

**Kernel**
: Noyau du système d'exploitation de la Xbox 360. Le numéro de version du kernel est important pour déterminer le type de modification applicable. Exemple : kernel 17559 (l'un des derniers).

**KV (KeyVault)**
: Partie de la NAND contenant les informations d'identification unique de la console (serial, CPU key, etc.). Critique pour la console, à sauvegarder impérativement.

---

## N

**NAND**
: Mémoire flash de la Xbox 360 contenant le système d'exploitation, le bootloader et les informations propres à la console. Une sauvegarde de la NAND est indispensable avant toute modification.

**NXE (New Xbox Experience)**
: Dashboard officiel de Microsoft pour la Xbox 360, introduit en 2008. Encore présent sur les consoles modifiées comme fallback, mais remplacé par Aurora dans l'usage courant.

---

## R

**RGH (Reset Glitch Hack)**
: Méthode de modification matérielle moderne, exploitant un glitch sur le signal de reset du CPU pour passer le bootloader en mode non sécurisé. Fonctionne sur la quasi-totalité des modèles et kernels. Variantes : RGH 1.0, RGH 2.0, RGH 3.0 (Squirt), Xecuter R-JTAG.

**ROL (Region Of Launch)**
: Zone géographique d'origine d'un jeu. Certains jeux sont protégés par région (région lock) et ne se lancent pas sur des consoles d'une autre zone. Les consoles modifiées peuvent souvent contourner cette limitation.

---

## S

**Skin**
: Voir *Thème*.

**SMC (System Management Controller)**
: Microcontrôleur gérant l'alimentation, les températures, les ventilateurs et les LEDs de la Xbox 360. Son firmware peut être modifié dans certaines configurations.

---

## T

**Thème / Skin Aurora**
: Ensemble de fichiers modifiant l'apparence visuelle d'Aurora (couleurs, textures, icônes, disposition). Stocké dans `/Aurora/Skins/`.

**TitleID**
: Identifiant unique de 8 caractères hexadécimaux attribué à chaque jeu Xbox 360. Utilisé par Aurora et DashLaunch pour identifier les jeux. Exemple : `4D5307E1` (Halo 3).

---

## X

**XEX**
: Format d'exécutable propre à la Xbox 360 (Xbox Executable). C'est le format des jeux, des applications et des plugins sur cette console.

**XBE**
: Format d'exécutable de la Xbox première du nom (pas la 360). À ne pas confondre avec XEX.

**XZP**
: Format d'archive utilisé par certains composants Aurora (notamment les thèmes et ressources graphiques).

---

!!! note "Glossaire en construction"
    Un terme manque ? [Propose-le sur GitHub](contribuer.md) !
