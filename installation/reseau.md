# Réseau & FTP

Connecter ta Xbox 360 au réseau local est une étape clé. Cela te permet de transférer
des fichiers depuis ton PC sans sortir de câbles ou de clés USB à chaque fois.

---

## Prérequis

- Console connectée au réseau (câble Ethernet recommandé, Wi-Fi possible via adaptateur)
- FTP activé dans Aurora ou DashLaunch
- Un client FTP sur ton PC ([FileZilla](https://filezilla-project.org/) est gratuit et recommandé)

---

## Trouver l'adresse IP de ta console

### Depuis Aurora

1. Dans Aurora, appuie sur le bouton **Start**
2. Va dans **Paramètres système > Réseau**
3. L'adresse IP de ta console s'affiche (ex: `192.168.1.42`)

### Depuis DashLaunch

Si tu as activé `ftpserver = on` dans DashLaunch, l'IP s'affiche souvent
dans les informations système du dashboard.

!!! tip "Attribuer une IP fixe"
    Pour éviter que l'IP change à chaque redémarrage, configure une **réservation DHCP**
    sur ton routeur (en liant l'adresse MAC de la console à une IP fixe).
    Cela rend la connexion FTP toujours immédiate, sans chercher l'IP.

---

## Se connecter en FTP avec FileZilla

1. Ouvre FileZilla
2. En haut, remplis les champs :

| Champ | Valeur |
|---|---|
| Hôte | `192.168.1.XX` (l'IP de ta console) |
| Identifiant | `xbox` |
| Mot de passe | `xbox` |
| Port | `21` |

3. Clique sur **Connexion rapide**

!!! info "Identifiants par défaut"
    Les identifiants `xbox` / `xbox` sont les valeurs par défaut d'Aurora.
    Tu peux les modifier dans les paramètres du plugin FTP d'Aurora.

---

## Naviguer dans les dossiers de la console

Une fois connecté, tu vois l'arborescence de ta console :

```
/
├── Hdd1/               ← Disque dur interne
│   ├── Aurora/         ← Ton installation Aurora
│   ├── Games/          ← Tes jeux
│   └── Content/        ← DLC, saves, profils
├── Usb0/               ← Clé USB (si branchée)
└── Dvd/                ← Lecteur optique (si disque inséré)
```

---

## Transférer des fichiers

### Depuis ton PC vers la console

1. Dans FileZilla, navigue vers le dossier cible sur la console (panneau droit)
2. Sur ton PC (panneau gauche), localise le fichier à envoyer
3. Glisse-dépose le fichier, ou fais un clic droit → **Envoyer**

### Depuis la console vers ton PC

Même principe en sens inverse : glisse depuis le panneau droit (console) vers le panneau gauche (PC).

!!! warning "Ne pas modifier les fichiers système"
    Évite de toucher aux dossiers système en dehors de `Aurora/`, `Games/` et `Content/`.
    Supprimer un mauvais fichier peut rendre la console instable.

---

## Automatiser les transferts (optionnel)

Pour les utilisateurs qui font des transferts fréquents, un script Python simple peut
accélérer le workflow :

```python
import ftplib

CONSOLE_IP = "192.168.1.42"
USER = "xbox"
PASS = "xbox"

with ftplib.FTP(CONSOLE_IP) as ftp:
    ftp.login(USER, PASS)
    ftp.cwd("/Hdd1/Aurora/Plugins/")
    with open("MonPlugin.xex", "rb") as f:
        ftp.storbinary("STOR MonPlugin.xex", f)
    print("Plugin envoyé avec succès.")
```

---

## Problèmes courants

??? question "FileZilla ne se connecte pas"
    - Vérifie que la console est allumée et sur Aurora
    - Vérifie que tu as la bonne IP (elle peut changer si DHCP)
    - Vérifie que le FTP est bien activé dans Aurora ou DashLaunch
    - Désactive temporairement le pare-feu Windows pour tester

??? question "La connexion se coupe pendant un transfert"
    - Utilise un câble Ethernet plutôt que le Wi-Fi
    - Réduis la taille des fichiers transférés en une seule fois
    - Dans FileZilla : `Édition > Paramètres > Connexion` → augmente le timeout

??? question "Je ne vois pas mes dossiers habituels"
    - Le FTP d'Aurora peut limiter l'accès à certains chemins selon sa configuration
    - Vérifie les paramètres du plugin FTP dans Aurora

---

## Prochaine étape

[→ Installer des plugins Aurora](../plugins/installation.md){ .md-button .md-button--primary }
