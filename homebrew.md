# Homebrew et applications

Les homebrews sont des programmes développés par la communauté, en dehors de tout cadre officiel.
Sur Xbox 360, ils peuvent prendre la forme de jeux, d'utilitaires, de lecteurs multimédias ou d'outils de diagnostic.

---

## Qu'est-ce qu'un homebrew ?

Un homebrew est un programme non signé par Microsoft, qui s'exécute uniquement sur une console modifiée (JTAG/RGH).
Il se présente comme un dossier contenant un fichier `default.xex`, exactement comme un jeu.

---

## Catégories de homebrews

### Lecteurs multimédias

**XBMC for Xbox 360**
Le célèbre media center, porté sur Xbox 360. Permet de lire des vidéos, musiques et images depuis
le réseau local ou un disque dur USB.

- Formats vidéo supportés : MKV, AVI, MP4, et bien d'autres
- Accès réseau : SMB, FTP, UPnP
- Interface : personnalisable via des skins

**Installation :**
1. Copie le dossier XBMC sur la console : `Hdd1:/Apps/XBMC/`
2. Lance depuis Aurora

---

**DVD2Xbox**
Utilitaire permettant de copier des disques directement sur le disque dur depuis le lecteur optique de la console.

!!! info "Usage légal"
    À utiliser uniquement pour copier tes propres disques physiques dont tu es propriétaire.

---

### Utilitaires système

**Xell Reloaded**
Chargeur de bas niveau utilisé lors du processus de modification RGH. Affiche des informations système
(CPU Key, console type, températures). Pas un homebrew d'usage quotidien mais indispensable à connaître.

**Neighbourhood**
Outil de débogage permettant d'explorer les fichiers de la console depuis un PC via protocole Xbox Neighborhood.
Utile pour les développeurs homebrew.

**Ping Sender**
Petit utilitaire pour tester la connectivité réseau de la console. Utile pour diagnostiquer des problèmes réseau.

---

### Jeux homebrew

Il existe quelques jeux développés spécifiquement pour Xbox 360 modifiée ou portés depuis d'autres plateformes.

!!! note "Communauté réduite"
    Le développement de jeux homebrew natifs pour Xbox 360 est resté très limité.
    La plupart des "jeux" disponibles sont des ports d'émulateurs ou de jeux open source.

**Cave Story 360**
Port du célèbre jeu indépendant Cave Story pour Xbox 360.

**Quake 360 / Doom 360**
Ports des classiques id Software, rendus possibles grâce aux sources ouvertes de ces jeux.

---

### Outils de diagnostic

**HDD Benchmark**
Teste les performances du disque dur interne de la console. Utile pour détecter un disque dur défaillant.

**Temperature Monitor**
Affiche en temps réel les températures du CPU et GPU de la console. Utile pour diagnostiquer des problèmes de chauffe.

---

## Installer un homebrew

Le processus est identique à l'installation d'un jeu :

1. Télécharge le homebrew depuis une source fiable (RealModScene, se7enSins)
2. Vérifie que l'archive contient bien un fichier `default.xex`
3. Copie le dossier sur la console via FTP : `Hdd1:/Apps/NomDuHomebrew/`
4. Dans Aurora, assure-toi que `Hdd1:/Apps/` est bien une source scannée
5. Lance le homebrew depuis Aurora

Structure recommandée :

```
Hdd1:/
├── Games/          ← Tes jeux
└── Apps/           ← Tes homebrews et utilitaires
    ├── XBMC/
    │   └── default.xex
    ├── DVD2Xbox/
    │   └── default.xex
    └── HDD-Benchmark/
        └── default.xex
```

---

## Sources fiables pour télécharger des homebrews

!!! warning "Prudence avec les sources"
    Télécharge uniquement depuis des sources reconnues par la communauté.
    Un fichier `.xex` malveillant pourrait endommager ta console.

- **RealModScene** — [realmodscene.com](https://www.realmodscene.com/)
- **Se7enSins** — [se7ensins.com](https://www.se7ensins.com/)
- **GitHub** — certains développeurs publient leurs homebrews directement en open source

---

## Développer son propre homebrew

Le développement de homebrews Xbox 360 est possible mais demande des outils et connaissances spécifiques.

**Outils nécessaires :**
- **XDK (Xbox Development Kit)** — SDK officiel Microsoft, difficile à trouver légalement
- **LibXenon** — Alternative open source au XDK, utilisée pour la plupart des homebrews récents
- **Langage** : C / C++

!!! info "Section avancée"
    Le développement homebrew Xbox 360 dépasse le cadre de ce guide d'introduction.
    Une section dédiée sera ajoutée ultérieurement. Si tu es développeur et veux contribuer
    à cette section, [tu es le bienvenu](../contribuer.md).

---

## Problèmes courants

??? question "Le homebrew ne s'affiche pas dans Aurora"
    - Vérifie que `Hdd1:/Apps/` est bien ajouté comme source dans Aurora
    - Vérifie que le dossier contient bien un fichier `default.xex`
    - Lance un scan manuel depuis les paramètres Aurora

??? question "Le homebrew crash au lancement"
    - Le homebrew est peut-être incompatible avec ta version de kernel ou de DashLaunch
    - Cherche sur RealModScene si d'autres ont le même problème
    - Essaie avec et sans certains plugins Aurora actifs (conflit possible)

??? question "XBMC ne trouve pas mes fichiers réseau"
    - Vérifie que le partage SMB est activé sur ton PC ou NAS
    - Entre l'IP du serveur manuellement dans XBMC plutôt que de passer par la découverte automatique

---

!!! note "Page en amélioration continue"
    Tu connais un homebrew fonctionnel non listé ici ? [Contribue au guide](../contribuer.md).
