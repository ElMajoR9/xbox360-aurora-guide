# Configurer DashLaunch

DashLaunch est un utilitaire système indispensable pour les Xbox 360 modifiées.
Il se charge avant le dashboard et permet de définir quel programme se lance au démarrage,
de patcher certains comportements système, et de contrôler les connexions réseau.

!!! warning "Prudence avec DashLaunch"
    Une mauvaise configuration de DashLaunch peut empêcher ta console de démarrer correctement.
    Lis cette page attentivement avant de modifier des paramètres. En cas de doute, laisse
    les options par défaut.

---

## Qu'est-ce que DashLaunch ?

DashLaunch s'exécute au niveau du **noyau système**, avant même le dashboard.
Ses fonctions principales :

- **Définir le dashboard par défaut** (Aurora, Freestyle Dash, NXE...)
- **Bloquer les connexions réseau** vers les serveurs Microsoft (pour protéger la console)
- **Activer le FTP** au démarrage
- **Patcher certains comportements** du système (températures, éjection de disque, etc.)
- **Charger des plugins** avant le dashboard

---

## Télécharger DashLaunch

!!! info "Où trouver DashLaunch ?"
    Recherche "DashLaunch Xbox 360" sur RealModScene ou se7enSins.
    La version 3.21 est la plus récente et stable au moment de la rédaction de ce guide.

---

## Installer DashLaunch

### Via Installer.xex

DashLaunch est fourni avec un fichier `Installer.xex` :

1. Copie le dossier DashLaunch sur ta console (clé USB ou FTP)
2. Lance `Installer.xex` depuis ton dashboard
3. L'interface de configuration s'affiche
4. Configure les options (voir ci-dessous)
5. Valide et redémarre la console

---

## Les paramètres essentiels

Voici les paramètres les plus importants à connaître pour une utilisation avec Aurora.

### Paramètre `defaultapp`

C'est le chemin vers le programme qui se lance au démarrage.

```
defaultapp = Hdd1:\Aurora\Aurora.xex
```

> 👉 C'est LE paramètre à configurer en priorité.

---

### Paramètres réseau

Ces paramètres contrôlent les connexions de ta console vers l'extérieur.

| Paramètre | Valeur recommandée | Explication |
|---|---|---|
| `pingpatch` | `on` | Empêche la console de pinguer les serveurs Xbox Live |
| `nxemenu` | `off` | Désactive le retour automatique au NXE |
| `devkitpatch` | `on` | Nécessaire pour certains homebrews |
| `nonetpatch` | `off` | Ne bloque pas entièrement le réseau local (laisser off pour FTP) |

!!! tip "Réseau local vs Xbox Live"
    Ces paramètres affectent les connexions vers Microsoft, pas ton réseau local.
    Tu peux toujours utiliser le FTP et accéder à Internet depuis la console
    avec les paramètres recommandés ci-dessus.

---

### Paramètre `ftpserver`

Active un serveur FTP au démarrage de la console, indépendamment d'Aurora.

```
ftpserver = on
ftpport   = 21
```

> 👉 Utile si tu veux accéder à la console en FTP avant même qu'Aurora soit chargé.

---

### Paramètre `tempctrl`

Contrôle la gestion de la température et de la vitesse des ventilateurs.

| Valeur | Comportement |
|---|---|
| `off` | Gestion automatique (défaut) |
| `1` à `6` | Niveau de ventilation forcé (6 = maximum) |

> La plupart des utilisateurs laissent ce paramètre sur `off`.

---

## Exemple de configuration complète (usage courant)

```ini
[Launch]
defaultapp  = Hdd1:\Aurora\Aurora.xex

[Patches]
pingpatch   = on
devkitpatch = on
nxemenu     = off
nonetpatch  = off

[Network]
ftpserver   = on
ftpport     = 21

[System]
tempctrl    = off
```

---

## Modifier la configuration depuis le PC

Il est possible d'éditer le fichier `launch.ini` directement depuis ton PC via FTP.

1. Connecte-toi en FTP à ta console
2. Navigue vers `Hdd1:/DashLaunch/`
3. Télécharge `launch.ini` sur ton PC
4. Modifie-le avec un éditeur de texte (Notepad, VS Code...)
5. Remets-le en place via FTP
6. Redémarre la console

---

## Problèmes courants

??? question "La console ne démarre plus sur Aurora"
    - Lance `Installer.xex` de DashLaunch depuis une clé USB
    - Vérifie que le chemin dans `defaultapp` est correct (sensible à la casse)
    - Vérifie que `Aurora.xex` est bien présent à l'emplacement indiqué

??? question "Le FTP ne fonctionne pas au démarrage"
    - Vérifie que `ftpserver = on` dans DashLaunch
    - Vérifie que ta console est bien connectée au réseau
    - Attends 20-30 secondes après le démarrage avant de te connecter

??? question "Comment revenir à la config par défaut ?"
    Lance l'`Installer.xex` de DashLaunch et utilise le bouton "Reset to defaults".

---

## Prochaine étape

[→ Configurer le réseau et le FTP](reseau.md){ .md-button .md-button--primary }
