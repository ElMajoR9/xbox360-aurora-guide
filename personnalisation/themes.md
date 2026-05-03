# Thèmes Aurora

Aurora permet de personnaliser son apparence via des thèmes (ou "skins").
Un thème modifie les couleurs, les textures, les icônes et parfois la disposition de l'interface.

---

## Installer un thème

### Étape 1 — Télécharger le thème

Un thème Aurora est généralement livré sous forme d'un dossier compressé.
Cherche des thèmes sur les forums Xbox 360 (RealModScene, se7enSins, Logic Sunrise).

### Étape 2 — Copier le thème sur la console

1. Décompresse l'archive sur ton PC
2. Connecte-toi à la console en FTP
3. Navigue vers `/Hdd1/Aurora/Skins/`
4. Copie le dossier du thème ici

Résultat attendu :

```
Hdd1:/Aurora/Skins/
├── Default/        ← Thème par défaut (ne pas supprimer)
└── MonTheme/       ← Ton nouveau thème
```

### Étape 3 — Activer le thème

1. Dans Aurora, va dans **Paramètres > Apparence** (ou **Skin**)
2. Sélectionne ton thème dans la liste
3. Valide — Aurora applique le thème immédiatement ou après redémarrage

---

## Créer son propre thème

!!! info "Section à compléter"
    La création de thèmes Aurora est un sujet avancé qui nécessite de comprendre
    la structure des fichiers `.xzp` et des fichiers de ressources Aurora.
    Cette section sera complétée prochainement. Tu connais le sujet ?
    [Contribue !](../contribuer.md)

---

## Problèmes courants

??? question "Le thème n'apparaît pas dans la liste"
    - Vérifie que le dossier du thème est bien dans `Skins/` et pas dans un sous-dossier supplémentaire
    - Un thème valide contient en général un fichier `skin.xzp` ou une structure de dossiers spécifique

??? question "Aurora crash après changement de thème"
    - Le thème est peut-être corrompu ou incompatible avec ta version d'Aurora
    - Reconnecte-toi en FTP et supprime le thème problématique
    - Aurora reviendra au thème par défaut au prochain démarrage

---

!!! note "Page en construction"
    Tu as des thèmes à partager ou de l'expérience sur leur création ? [Contribue au guide](../contribuer.md).
