# Multijoueur local et LAN

Une Xbox 360 modifiée peut toujours profiter du multijoueur — en local sur le même écran,
en écran partagé, ou en réseau local entre plusieurs consoles.

---

## Modes multijoueur disponibles

| Mode | Description | Fonctionne sur console modifiée |
|---|---|---|
| Écran partagé (splitscreen) | 2 à 4 joueurs sur le même écran, même console | ✅ Oui |
| Multijoueur local (LAN) | Plusieurs consoles en réseau local | ✅ Oui |
| Système Link | Protocol Xbox de jeu en réseau local | ✅ Oui |
| Xbox Live en ligne | Jeu en ligne via les serveurs Microsoft | ❌ Déconseillé (risque de ban) |

---

## Écran partagé (Splitscreen)

Le splitscreen ne nécessite aucune configuration particulière. Branche simplement plusieurs
manettes sur la console et suis les instructions du jeu pour lancer une partie multijoueur locale.

La plupart des jeux Xbox 360 supportant le splitscreen fonctionnent normalement sur une console modifiée.

---

## Système Link (LAN entre plusieurs consoles)

Le Système Link permet de connecter plusieurs Xbox 360 en réseau local pour jouer ensemble,
sans passer par Internet ni par les serveurs Xbox Live.

### Prérequis

- 2 consoles Xbox 360 (modifiées ou non) avec le même jeu
- Un switch ou routeur réseau
- Un câble Ethernet par console
- Un profil joueur sur chaque console

### Configuration

1. Connecte chaque console au même réseau local via câble Ethernet
2. Lance le jeu sur chaque console
3. Dans le menu du jeu, cherche l'option **Système Link** ou **LAN**
4. Une console crée la session, les autres la rejoignent

!!! tip "Même version du jeu"
    Pour que le Système Link fonctionne, toutes les consoles doivent avoir la même version
    (même région, même mise à jour) du jeu.

---

## XLink Kai — Multijoueur en ligne via tunnel

XLink Kai est un logiciel qui "simule" un réseau local sur Internet, permettant de jouer
en Système Link avec des joueurs du monde entier sans passer par Xbox Live.

### Comment ça fonctionne

XLink Kai crée un tunnel réseau entre les consoles. La Xbox 360 croit jouer en LAN local
alors qu'elle joue en réalité avec des joueurs distants.

### Ce qu'il faut

- Un PC connecté au même réseau que la console
- Le logiciel XLink Kai installé sur le PC ([www.teamxlink.co.uk](https://www.teamxlink.co.uk/))
- Un compte XLink Kai gratuit
- DashLaunch configuré pour ne pas bloquer le trafic réseau local

### Configuration de base

1. Installe XLink Kai sur ton PC
2. Lance XLink Kai et connecte-toi à ton compte
3. Dans l'interface XLink Kai, trouve l'arène correspondant à ton jeu
4. Sur la console, lance le jeu en mode Système Link
5. XLink Kai détecte la session et la rend visible aux autres joueurs sur Internet

!!! warning "Compatibilité variable"
    Tous les jeux ne fonctionnent pas avec XLink Kai. Consulte la liste de compatibilité
    sur le site officiel XLink Kai avant de tenter.

---

## Jeux recommandés pour le multijoueur local

### Splitscreen incontournables

- **Halo 3** — Jusqu'à 4 joueurs en splitscreen
- **Halo: Reach** — Splitscreen et Système Link
- **Call of Duty (série)** — Splitscreen 2 joueurs
- **Gears of War (série)** — Coopération en splitscreen
- **Borderlands (série)** — 2 joueurs en splitscreen
- **Forza Motorsport** — Jusqu'à 4 joueurs en splitscreen

### Système Link incontournables

- **Halo 3** — Hasta 16 joueurs en Système Link
- **Halo: Reach** — Système Link complet
- **Left 4 Dead / L4D2** — Coopération en LAN
- **Forza Motorsport** — Courses en réseau local

---

## Problèmes courants

??? question "Le jeu ne propose pas l'option Système Link"
    - Certains jeux ne supportent pas le Système Link — vérifie sur le boîtier ou en ligne
    - Assure-toi que toutes les consoles sont bien connectées au même réseau local
    - Certains jeux demandent un profil Xbox Live actif même pour le Système Link local

??? question "XLink Kai ne détecte pas ma console"
    - Vérifie que le PC et la console sont sur le même réseau local
    - Désactive temporairement le pare-feu Windows sur le PC
    - Dans DashLaunch, vérifie que `nonetpatch = off` pour ne pas bloquer le trafic

??? question "Le Système Link fonctionne mais les parties se déconnectent"
    - Utilise des câbles Ethernet plutôt que le Wi-Fi
    - Vérifie que toutes les consoles ont la même version du jeu
    - Réduis le nombre de joueurs si le réseau est surchargé

---

!!! note "Page en amélioration continue"
    Tu as de l'expérience avec XLink Kai ou le multijoueur LAN ? [Contribue au guide](../contribuer.md).
