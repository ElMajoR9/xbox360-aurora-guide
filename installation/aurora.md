# Installer Aurora Dashboard

Aurora Dashboard est l'interface principale utilisée sur les Xbox 360 modifiées (JTAG/RGH).
Il remplace le dashboard officiel de Microsoft et permet de lancer des jeux, gérer des plugins,
personnaliser l'interface et accéder à sa console via le réseau.

---

## Prérequis

Avant d'installer Aurora, tu dois avoir :

- Une Xbox 360 avec une modification **JTAG** ou **RGH** opérationnelle
- Un accès à la NAND ou un moyen de déposer des fichiers sur la console (clé USB ou FTP si un autre dashboard est déjà installé)
- La dernière version d'Aurora ([voir les sources officielles](#telecharger-aurora))

!!! warning "JTAG ou RGH ?"
    Si tu n'es pas sûr du type de modification de ta console, consulte le [glossaire](../glossaire.md).
    Les deux types sont compatibles avec Aurora.

---

## Télécharger Aurora { #telecharger-aurora }

La version de référence est **Aurora 0.7b.2**.

!!! info "Où télécharger ?"
    Aurora est distribué par sa communauté d'origine. Recherche "Aurora Dashboard 0.7b.2"
    sur RealModScene ou se7enSins. Vérifie toujours l'intégrité du fichier (MD5/SHA1)
    avant de l'installer sur ta console.

Le fichier téléchargé contient en général :

```
Aurora/
├── Aurora.xex          ← Fichier principal
├── Data/               ← Données d'Aurora
├── Plugins/            ← Dossier des plugins (vide à l'install)
└── Skins/              ← Thèmes visuels
```

---

## Structure des fichiers sur la console

Aurora doit être placé à la racine d'un disque reconnu par la console.
L'emplacement recommandé :

```
Hdd1:/Aurora/           ← Installation principale (disque dur interne)
```

Alternative si pas de disque dur :

```
Usb0:/Aurora/           ← Clé USB (moins stable pour un usage permanent)
```

---

## Installation pas à pas

### Étape 1 — Copier Aurora sur la console

**Via clé USB :**

1. Formate une clé USB en FAT32 sur ton PC
2. Crée un dossier `Aurora` à la racine de la clé
3. Copie le contenu du zip dans ce dossier
4. Branche la clé sur ta Xbox 360

**Via FTP (si un dashboard est déjà installé) :**

1. Active le FTP depuis ton dashboard actuel
2. Connecte-toi avec un client FTP (ex: FileZilla) à l'IP de ta console
3. Copie le dossier `Aurora` vers `Hdd1:/`

---

### Étape 2 — Lancer Aurora pour la première fois

1. Depuis ton dashboard actuel, navigue vers l'emplacement où tu as copié Aurora
2. Lance le fichier `Aurora.xex`
3. Aurora démarre et effectue sa configuration initiale automatiquement

!!! tip "Premier lancement"
    Le premier lancement peut prendre 1 à 2 minutes le temps qu'Aurora génère
    ses fichiers de configuration et scanne les sources de jeux.

---

### Étape 3 — Configurer les sources de jeux

Aurora doit savoir où chercher tes jeux. Pour cela :

1. Dans Aurora, va dans **Paramètres** (icône engrenage)
2. Puis **Gestion des sources**
3. Ajoute les chemins où sont stockés tes jeux, par exemple :
   - `Hdd1:/Games/`
   - `Usb0:/Games/`

Aurora scannera ces dossiers et affichera les jeux détectés dans la bibliothèque.

---

### Étape 4 — Configurer DashLaunch pour booter sur Aurora

Pour qu'Aurora se lance automatiquement au démarrage de la console, il faut configurer DashLaunch.

[→ Configurer DashLaunch](dashlaunch.md){ .md-button }

---

## Structure des dossiers Aurora (après installation)

```
Hdd1:/Aurora/
├── Aurora.xex
├── Data/
│   ├── Aurora.db           ← Base de données de ta bibliothèque
│   ├── settings.db         ← Tes paramètres
│   └── cache/              ← Cache artworks
├── Plugins/
│   └── (vide au départ)
├── Skins/
│   └── Default/            ← Thème par défaut
└── Logs/
    └── Aurora.log          ← Journal des événements
```

---

## Problèmes courants

??? question "Aurora ne se lance pas"
    - Vérifie que `Aurora.xex` est bien présent dans le dossier
    - Vérifie que les fichiers du dossier `Data/` sont intacts
    - Essaie depuis une clé USB pour écarter un problème de disque dur

??? question "Mes jeux n'apparaissent pas"
    - Vérifie les chemins dans **Paramètres > Gestion des sources**
    - Les jeux doivent contenir un fichier `default.xex` à leur racine
    - Lance un scan manuel depuis les paramètres

??? question "L'interface est très lente"
    - Si tu as beaucoup de jeux, le scan initial peut prendre du temps
    - Attends qu'Aurora finisse de générer le cache d'artworks

---

## Prochaine étape

Une fois Aurora installé et fonctionnel, l'étape suivante est de configurer DashLaunch
pour un démarrage automatique et un comportement stable.

[→ Configurer DashLaunch](dashlaunch.md){ .md-button .md-button--primary }

---

!!! note "Page en amélioration continue"
    Tu as constaté une erreur ou tu veux ajouter une étape ? [Contribue au guide](../contribuer.md).
