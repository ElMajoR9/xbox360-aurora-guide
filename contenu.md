# Gestion du contenu

Sur une Xbox 360 sous Aurora, les jeux et contenus peuvent se présenter sous différents formats.
Cette page explique les différences, comment les organiser, et comment les faire fonctionner correctement.

---

## Les formats de jeux

### Format ISO / XGD

Un fichier ISO est une image complète d'un disque Xbox 360. C'est le format brut,
tel qu'il sort d'un lecteur optique.

- Extension : `.iso`
- Taille : généralement entre 2 Go et 8 Go
- Compatibilité Aurora : **non natif** — Aurora ne lit pas les ISO directement
- Solution : convertir en GOD ou extraire le contenu (voir ci-dessous)

---

### Format GOD (Games on Demand)

Le format GOD est le format utilisé par Microsoft pour les jeux téléchargés depuis le Xbox Live Marketplace.
C'est aussi le format recommandé pour stocker ses jeux sur le disque dur d'une Xbox 360 modifiée.

- Structure : un dossier avec un fichier sans extension contenant les données
- Compatibilité Aurora : ✅ natif, Aurora les détecte automatiquement
- Avantage : pas de fichier `default.xex` visible, gestion propre par Aurora

Structure typique d'un jeu GOD :

```
Hdd1:/Games/
└── 4D5307E1/           ← TitleID du jeu
    └── 000D0000/       ← Dossier de contenu
        └── [fichier sans extension]  ← Données du jeu
```

---

### Format XEX (dossier extrait)

C'est le format le plus courant pour les homebrews et les jeux extraits depuis un ISO.
Le jeu est représenté par un dossier contenant un fichier `default.xex`.

- Structure : dossier avec `default.xex` à la racine
- Compatibilité Aurora : ✅ natif, c'est le format préféré pour les homebrews
- Avantage : simple, universel, facile à gérer en FTP

Structure typique :

```
Hdd1:/Games/
└── Halo 3/
    ├── default.xex     ← Fichier principal (obligatoire)
    ├── default.xex.map
    └── [autres fichiers du jeu]
```

!!! tip "Format recommandé"
    Pour les jeux, utilise le format XEX (dossier extrait) — c'est le plus simple à gérer,
    le plus compatible avec Aurora, et le plus facile à transférer via FTP.

---

## Convertir un ISO en format lisible par Aurora

Aurora ne lit pas les ISO directement. Il faut d'abord les convertir ou les extraire.

### Option 1 — Extraire en format XEX (recommandé)

Depuis ton PC, tu peux extraire le contenu d'un ISO avec des outils adaptés.
Le résultat est un dossier contenant `default.xex` que tu copies ensuite sur la console via FTP.

### Option 2 — Convertir en GOD

La conversion ISO → GOD se fait depuis le PC avec des utilitaires dédiés.
Le résultat est un dossier au format GOD que tu places dans la structure correcte sur le disque dur.

!!! warning "Usage légal"
    Ces opérations sont à effectuer uniquement sur des jeux dont tu es propriétaire.
    Ce guide ne fournit pas de liens vers des outils de conversion ou des ISOs.

---

## Gérer les DLC

Les DLC (contenus téléchargeables) sur Xbox 360 sont des fichiers stockés dans un dossier `Content`.

### Structure des DLC

```
Hdd1:/Content/
└── 0000000000000000/       ← Dossier profil (ou 0000... pour les DLC sans profil)
    └── [TitleID du jeu]/   ← Ex: 4D5307E1 pour Halo 3
        └── 000B0000/       ← Type de contenu (DLC)
            └── [fichier DLC sans extension]
```

### Installer un DLC via FTP

1. Connecte-toi à la console en FTP
2. Navigue vers `Hdd1:/Content/0000000000000000/`
3. Crée un dossier avec le TitleID du jeu si il n'existe pas
4. À l'intérieur, crée un dossier `000B0000`
5. Copie le fichier DLC dans ce dossier
6. Relance le jeu — le DLC devrait être détecté automatiquement

!!! info "TitleID"
    Le TitleID est l'identifiant unique du jeu (8 caractères hexadécimaux).
    Aurora l'affiche dans les informations du jeu. Consulte le [glossaire](../glossaire.md) pour plus de détails.

---

## Gérer les profils et sauvegardes

### Emplacement des sauvegardes

Les sauvegardes de jeux sont stockées dans :

```
Hdd1:/Content/
└── [ID du profil]/         ← Identifiant de ton profil Xbox
    └── [TitleID du jeu]/
        └── 00000001/       ← Dossier saves
            └── [fichier de sauvegarde]
```

### Sauvegarder ses données via FTP

1. Connecte-toi en FTP
2. Navigue vers `Hdd1:/Content/`
3. Copie le dossier correspondant à ton profil sur ton PC
4. C'est ta sauvegarde — conserve-la précieusement

!!! warning "Sauvegarde régulière"
    Le disque dur d'une Xbox 360 peut lâcher sans prévenir. Sauvegarde régulièrement
    tes profils et sauvegardes vers ton PC via FTP.

---

## Organiser sa bibliothèque dans Aurora

### Bonnes pratiques de nommage

Aurora utilise le nom du dossier pour identifier le jeu avant de récupérer ses métadonnées.
Un nom de dossier propre facilite la détection automatique :

| À éviter | Recommandé |
|---|---|
| `Halo3_PAL_RGH_v2` | `Halo 3` |
| `GAME_4D5307E1` | `Halo 3` |
| `halo3final` | `Halo 3` |

### Configurer les sources dans Aurora

1. Dans Aurora, va dans **Paramètres > Gestion des sources**
2. Ajoute tous les chemins où sont stockés tes jeux
3. Lance un **scan manuel** après chaque ajout de jeu

### Forcer la récupération des métadonnées

Si Aurora n'affiche pas le bon titre ou artwork pour un jeu :

1. Sélectionne le jeu dans la bibliothèque
2. Appuie sur **Y**
3. Choisis **Rafraîchir les informations** ou **Rechercher manuellement**
4. Entre le nom exact du jeu pour trouver les bonnes métadonnées

---

## Problèmes courants

??? question "Mon jeu apparaît sans titre ni artwork"
    - Vérifie que le dossier du jeu est bien nommé avec le titre du jeu
    - Lance une recherche manuelle depuis Aurora (touche Y sur le jeu)
    - Si Unity est configuré dans Aurora, les métadonnées se récupèrent automatiquement

??? question "Mon DLC n'est pas détecté en jeu"
    - Vérifie la structure des dossiers (TitleID correct, dossier `000B0000`)
    - Le DLC doit correspondre exactement à la région et la version du jeu
    - Relance le jeu après avoir copié le DLC

??? question "Aurora détecte un jeu en double"
    - Tu as probablement le même jeu dans deux dossiers sources différents
    - Supprime un des doublons ou retire la source concernée dans Aurora

??? question "Mes sauvegardes ont disparu après une réinstallation"
    - Les sauvegardes sont liées au profil Xbox, pas au jeu
    - Si tu as conservé une copie FTP du dossier `Content/`, restaure-le sur la console

---

!!! note "Page en amélioration continue"
    Tu as des précisions à apporter ou une situation non couverte ici ?
    [Contribue au guide](../contribuer.md).
