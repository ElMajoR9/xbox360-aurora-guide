# Sauvegardes et profils

Gérer ses sauvegardes et profils correctement est essentiel pour ne pas perdre sa progression.
Cette page explique comment les localiser, les sauvegarder et les restaurer.

---

## Comprendre la structure des profils

Sur Xbox 360, chaque joueur a un **profil** qui contient ses informations, ses succès et ses sauvegardes.
Un profil est identifié par un ID unique de 16 caractères hexadécimaux.

```
Hdd1:/Content/
└── E000ABCD12345678/       ← Ton ID de profil
    ├── FFFE07D1/            ← Données du profil lui-même
    │   └── 00010000/
    │       └── [fichier profil]
    └── [TitleID du jeu]/    ← Ex: 4D5307E1
        └── 00000001/        ← Sauvegardes
            └── [fichier save]
```

---

## Trouver l'ID de ton profil

### Depuis Aurora

1. Dans Aurora, va dans **Paramètres > Profils**
2. Sélectionne ton profil
3. L'ID s'affiche dans les informations du profil

### Depuis le dossier Content en FTP

1. Connecte-toi en FTP
2. Navigue vers `Hdd1:/Content/`
3. Les dossiers dont le nom fait 16 caractères hexadécimaux sont tes profils
4. Le tien est celui qui correspond à ton gamertag

---

## Sauvegarder ses données

!!! warning "Sauvegarde régulière indispensable"
    Le disque dur d'une Xbox 360 peut tomber en panne sans prévenir.
    Sauvegarde tes données sur PC régulièrement, au minimum une fois par mois.

### Sauvegarder tout le dossier Content via FTP

C'est la méthode la plus simple et la plus complète.

1. Connecte-toi en FTP avec FileZilla
2. Dans le panneau console (droite), navigue vers `Hdd1:/Content/`
3. Fais un clic droit sur le dossier de ton profil → **Télécharger**
4. Choisis un emplacement sur ton PC
5. Attends la fin du transfert

!!! tip "Automatiser avec un script"
    Tu peux automatiser cette sauvegarde avec un script Python qui se connecte en FTP
    et copie le dossier automatiquement. Voir la section [Réseau & FTP](../installation/reseau.md)
    pour un exemple de script.

---

### Sauvegarder uniquement les saves d'un jeu

Si tu veux sauvegarder les saves d'un jeu spécifique :

1. Trouve le TitleID du jeu dans Aurora (touche Y sur le jeu → informations)
2. En FTP, navigue vers :
   ```
   Hdd1:/Content/[TON_ID_PROFIL]/[TITLEID_DU_JEU]/00000001/
   ```
3. Copie le contenu de ce dossier sur ton PC

---

## Restaurer ses sauvegardes

### Restaurer depuis une sauvegarde FTP

1. Connecte-toi en FTP
2. Navigue vers l'emplacement d'origine sur la console
3. Copie les fichiers depuis ton PC vers la console
4. Relance le jeu — la sauvegarde devrait être détectée

!!! warning "Compatibilité des saves"
    Une sauvegarde est liée à un profil spécifique. Si tu changes de profil,
    certains jeux refuseront de charger la sauvegarde d'un autre profil.

---

## Créer et gérer plusieurs profils

### Créer un nouveau profil

Dans Aurora, accède à la gestion des profils et crée un nouveau profil local.
Un profil local n'est pas lié au Xbox Live — il est stocké uniquement sur la console.

### Changer de profil actif

1. Dans Aurora, va dans **Paramètres > Profils**
2. Sélectionne le profil à activer
3. Valide — Aurora utilise désormais ce profil pour les sauvegardes

---

## Problèmes courants

??? question "Ma sauvegarde a disparu après un crash"
    - Vérifie dans `Hdd1:/Content/[TON_ID]/[TITLEID]/00000001/` si le fichier est toujours là
    - Si le fichier est corrompu (taille 0 ou anormalement petite), il faut restaurer une sauvegarde PC
    - Pour l'avenir : sauvegarde régulièrement via FTP

??? question "Le jeu ne reconnaît pas ma sauvegarde"
    - La sauvegarde doit être dans le dossier du bon profil
    - Vérifie que tu joues avec le même profil que celui utilisé lors de la sauvegarde
    - Certains jeux lient la sauvegarde au profil Xbox Live — une sauvegarde d'un autre compte ne fonctionnera pas

??? question "Je veux transférer mes saves vers une autre console"
    - Copie le dossier Content de ton profil sur PC via FTP depuis la console source
    - Copie ce même dossier vers la console destination via FTP
    - Assure-toi que l'ID de profil est identique sur les deux consoles

??? question "Aurora affiche un message d'erreur au chargement du profil"
    - Le fichier profil est peut-être corrompu
    - Tente de restaurer le profil depuis une sauvegarde PC
    - En dernier recours, crée un nouveau profil

---

!!! note "Page en amélioration continue"
    Une situation non couverte ici ? [Contribue au guide](../contribuer.md).
