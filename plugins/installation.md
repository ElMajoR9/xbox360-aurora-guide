# Installer un plugin Aurora

Les plugins permettent d'étendre les fonctionnalités d'Aurora.
Un plugin peut ajouter un serveur FTP, afficher des informations système, gérer du contenu, etc.

---

## Comment fonctionne un plugin ?

Un plugin Aurora est un fichier `.xex` (exécutable Xbox 360) placé dans le bon dossier.
Aurora le détecte au démarrage et l'exécute en arrière-plan ou l'intègre à l'interface.

---

## Structure d'un plugin

Un plugin est généralement livré sous forme d'un dossier ou d'une archive contenant :

```
MonPlugin/
├── MonPlugin.xex       ← Le plugin lui-même
├── settings.xml        ← Configuration (optionnel)
└── README.txt          ← Instructions de l'auteur (lis-le !)
```

---

## Installer un plugin pas à pas

### Étape 1 — Télécharger le plugin

Télécharge le plugin depuis sa source officielle.

!!! warning "Sources fiables uniquement"
    Ne télécharge des plugins que depuis des sources reconnues : RealModScene, se7enSins,
    ou le GitHub de l'auteur. Vérifie la date de publication et les commentaires de la communauté.

---

### Étape 2 — Copier le plugin sur la console

Via FTP (méthode recommandée) :

1. Connecte-toi à la console avec FileZilla
2. Navigue vers `/Hdd1/Aurora/Plugins/`
3. Crée un sous-dossier avec le nom du plugin (bonne pratique)
4. Copie le fichier `.xex` (et les fichiers associés) dans ce dossier

Résultat attendu :

```
Hdd1:/Aurora/Plugins/
└── MonPlugin/
    └── MonPlugin.xex
```

---

### Étape 3 — Activer le plugin dans Aurora

1. Dans Aurora, va dans **Paramètres > Plugins**
2. La liste des plugins détectés s'affiche
3. Active le plugin souhaité
4. **Redémarre Aurora** (ou la console entière) pour que le plugin soit chargé

!!! info "Redémarrage nécessaire"
    La plupart des plugins nécessitent un redémarrage d'Aurora pour être actifs.
    Certains le précisent dans leur README.

---

## Vérifier qu'un plugin est actif

Après redémarrage, retourne dans **Paramètres > Plugins**.
Le plugin actif affiche un statut "Chargé" ou similaire.
Consulte la documentation du plugin pour savoir où ses fonctions apparaissent dans l'interface.

---

## Désinstaller un plugin

1. Désactive le plugin dans **Paramètres > Plugins**
2. Supprime son dossier dans `/Hdd1/Aurora/Plugins/` via FTP
3. Redémarre Aurora

---

## Problèmes courants

??? question "Le plugin n'apparaît pas dans la liste"
    - Vérifie que le fichier `.xex` est bien dans `/Hdd1/Aurora/Plugins/`
    - Le dossier doit être dans `Plugins/`, pas ailleurs
    - Redémarre complètement Aurora après avoir copié le plugin

??? question "Aurora freeze au démarrage après l'ajout d'un plugin"
    - Le plugin est probablement incompatible avec ta version d'Aurora
    - Connecte-toi en FTP et supprime le plugin depuis ton PC
    - Consulte la [liste de compatibilité](compatibilite.md) avant d'installer

??? question "Le plugin s'installe mais ne fait rien"
    - Lis le README du plugin : il peut nécessiter une configuration supplémentaire
    - Certains plugins ont une interface accessible via le menu Aurora (touche Back ou Start)

---

## Prochaine étape

[→ Voir la liste de compatibilité des plugins](compatibilite.md){ .md-button .md-button--primary }
