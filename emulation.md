# Émulation sur Xbox 360

La Xbox 360 est suffisamment puissante pour émuler de nombreuses consoles rétro.
Cette page recense les émulateurs disponibles, leur compatibilité et comment les installer sous Aurora.

---

## Pourquoi émuler sur Xbox 360 ?

- Grand écran TV, manette Xbox confortable, salon
- La console est déjà branchée et configurée
- Bonne puissance pour les consoles 8-bit et 16-bit, correcte pour 32-bit
- Alternative intéressante à un Raspberry Pi pour du rétro-gaming salon

---

## Émulateurs disponibles

### NES — FCE Ultra GX 360

Émulateur NES porté sur Xbox 360, basé sur FCE Ultra GX (version Wii).

| Infos | Détails |
|---|---|
| Compatibilité | Très haute — quasi tous les jeux NES |
| Performances | Excellentes |
| Format ROMs | `.nes` |
| Statut | Fonctionnel sous Aurora |

**Installation :**

1. Télécharge FCE Ultra GX 360 (cherche sur RealModScene)
2. Copie le dossier sur la console via FTP : `Hdd1:/Emulators/FCEUX/`
3. Place tes ROMs NES dans un dossier `Hdd1:/Roms/NES/`
4. Lance `default.xex` depuis Aurora

---

### SNES — Snes9x 360

Émulateur Super Nintendo pour Xbox 360, port de Snes9x.

| Infos | Détails |
|---|---|
| Compatibilité | Haute — la majorité des jeux SNES |
| Performances | Très bonnes, quelques jeux avec effets spéciaux (SuperFX) peuvent ralentir |
| Format ROMs | `.smc`, `.sfc`, `.zip` |
| Statut | Fonctionnel sous Aurora |

**Installation :**

1. Télécharge Snes9x 360 (cherche sur RealModScene)
2. Copie le dossier sur la console : `Hdd1:/Emulators/Snes9x/`
3. Place tes ROMs SNES dans `Hdd1:/Roms/SNES/`
4. Lance `default.xex` depuis Aurora

---

### Game Boy / GBC / GBA — VBA-M 360

Émulateur Game Boy Advance (et versions précédentes) pour Xbox 360.

| Infos | Détails |
|---|---|
| Compatibilité | Bonne pour GB/GBC, correcte pour GBA |
| Performances | Bonnes dans l'ensemble |
| Format ROMs | `.gb`, `.gbc`, `.gba` |
| Statut | Fonctionnel sous Aurora |

---

### Mega Drive / Genesis — Genesis Plus GX 360

Port de Genesis Plus GX, référence de l'émulation Mega Drive.

| Infos | Détails |
|---|---|
| Compatibilité | Très haute |
| Performances | Excellentes |
| Format ROMs | `.md`, `.bin`, `.smd`, `.zip` |
| Statut | Fonctionnel sous Aurora |

---

### PlayStation 1 — PCSX ReARMed / pSX

L'émulation PS1 sur Xbox 360 est fonctionnelle mais demande plus de configuration.

| Infos | Détails |
|---|---|
| Compatibilité | Correcte — certains jeux ont des problèmes graphiques |
| Performances | Variables selon les jeux |
| Format ROMs | `.bin` + `.cue`, `.img`, `.iso` |
| BIOS requis | Oui — BIOS PS1 original nécessaire |
| Statut | Fonctionnel avec configuration |

!!! warning "BIOS requis"
    L'émulation PS1 nécessite un fichier BIOS original (`SCPH1001.BIN` ou similaire).
    Ce fichier doit provenir de ta propre console PlayStation. Ce guide ne fournit pas de BIOS.

---

### N64 — Mupen64Plus 360

L'émulation N64 est plus exigeante et la compatibilité est inégale.

| Infos | Détails |
|---|---|
| Compatibilité | Variable — les jeux simples fonctionnent bien, les jeux complexes moins |
| Performances | Correctes pour les jeux moins exigeants |
| Format ROMs | `.z64`, `.n64`, `.v64` |
| Statut | Fonctionnel mais limité |

!!! info "Attentes réalistes"
    L'émulation N64 sur Xbox 360 n'est pas parfaite. Des jeux comme Mario 64 ou Ocarina of Time
    tournent bien, mais certains titres auront des problèmes graphiques ou de performances.

---

## Organiser ses émulateurs dans Aurora

### Structure recommandée

```
Hdd1:/
├── Emulators/
│   ├── FCEUX/
│   │   └── default.xex
│   ├── Snes9x/
│   │   └── default.xex
│   ├── VBA-M/
│   │   └── default.xex
│   └── GenesisPlus/
│       └── default.xex
└── Roms/
    ├── NES/
    ├── SNES/
    ├── GBA/
    ├── MegaDrive/
    └── PS1/
```

### Ajouter les émulateurs dans Aurora

1. Dans Aurora, va dans **Paramètres > Gestion des sources**
2. Ajoute `Hdd1:/Emulators/` comme source
3. Aurora détecte les émulateurs comme des applications
4. Tu peux leur assigner un artwork manuellement (touche Y)

---

## Configurer les manettes dans les émulateurs

La plupart des émulateurs Xbox 360 ont une configuration de manette par défaut.
Pour la modifier :

1. Lance l'émulateur depuis Aurora
2. Accède au menu de l'émulateur (souvent **Back** ou **Guide**)
3. Va dans **Settings > Controls** ou **Configuration > Manette**
4. Remappes les boutons selon ta préférence

---

## Problèmes courants

??? question "L'émulateur se lance mais les ROMs n'apparaissent pas"
    - Vérifie que le chemin vers tes ROMs est correctement configuré dans l'émulateur
    - Ouvre les paramètres de l'émulateur et renseigne le dossier ROMs
    - Les ROMs doivent être dans le bon format (voir tableau par émulateur)

??? question "Les jeux sont lents ou ont des ralentissements"
    - Essaie de désactiver les filtres graphiques dans les paramètres de l'émulateur
    - Certains jeux sont naturellement difficiles à émuler (SuperFX, jeux N64 complexes)
    - Vérifie que tu utilises la dernière version de l'émulateur disponible

??? question "Pas de son ou son déformé"
    - Va dans les paramètres audio de l'émulateur
    - Essaie différents modes audio (synchrone / asynchrone)

??? question "L'émulation PS1 ne démarre pas"
    - Vérifie que le fichier BIOS est présent et correctement nommé
    - Place le BIOS dans le dossier indiqué par l'émulateur (souvent un dossier `BIOS/`)

---

!!! note "Page en amélioration continue"
    Tu as testé un émulateur non listé ou tu as des précisions à apporter ?
    [Contribue au guide](../contribuer.md).
