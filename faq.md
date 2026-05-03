# Foire aux questions (FAQ)

Les questions les plus fréquemment posées sur les forums Xbox 360 homebrew, regroupées ici.

---

## Général

??? question "C'est quoi la différence entre JTAG et RGH ?"
    Les deux sont des méthodes de modification matérielle de la Xbox 360 qui permettent
    d'exécuter du code non signé (homebrews, dashboards alternatifs, etc.).

    - **JTAG** : Méthode plus ancienne, ne fonctionne que sur les consoles avec un noyau système
      (kernel) égal ou inférieur à 7371. Très peu de consoles éligibles aujourd'hui.
    - **RGH** (Reset Glitch Hack) : Méthode moderne, fonctionne sur la quasi-totalité des modèles
      et kernels. Temps de démarrage légèrement plus long sur certains modèles (RGH 1.0),
      quasiment instantané sur RGH 2.0 et RGH 3.0.

    → Consulte le [glossaire](glossaire.md) pour plus de détails.

??? question "Puis-je aller sur le Xbox Live avec une console JTAG/RGH ?"
    C'est fortement déconseillé. Microsoft peut détecter les consoles modifiées et les **bans**
    définitivement du Xbox Live. Ce guide ne couvre pas l'utilisation du Xbox Live sur console modifiée.

??? question "Aurora est-il toujours maintenu en 2026 ?"
    Aurora 0.7b.2 est la dernière version publique. Le développement actif semble arrêté,
    mais la version disponible reste stable et fonctionnelle pour un usage quotidien.

---

## Installation

??? question "Dans quel ordre dois-je installer les composants ?"
    L'ordre recommandé est :

    1. Ta console doit déjà être modifiée (JTAG ou RGH)
    2. Installe **DashLaunch** en premier
    3. Installe **Aurora**
    4. Configure DashLaunch pour démarrer sur Aurora
    5. Configure le réseau et le FTP
    6. Ajoute les plugins et personnalisations

??? question "J'ai perdu mon dashboard par défaut. Comment y revenir ?"
    Lance l'`Installer.xex` de DashLaunch depuis une clé USB et change le chemin
    de `defaultapp` vers le dashboard souhaité. Si tu veux revenir au NXE (dashboard Microsoft),
    laisse le champ vide.

---

## Jeux & Bibliothèque

??? question "Mes jeux n'apparaissent pas dans Aurora"
    Vérifie les points suivants :

    1. Tes jeux sont dans un dossier ajouté comme **source** dans Aurora (Paramètres > Sources)
    2. Chaque jeu a bien un fichier `default.xex` à sa racine
    3. Lance un **scan manuel** depuis les paramètres d'Aurora
    4. Si tu viens d'ajouter des jeux, attends que le scan se termine

??? question "Quelle est la structure correcte d'un jeu dans Aurora ?"
    ```
    Hdd1:/Games/
    └── NomDuJeu/
        ├── default.xex         ← Obligatoire
        └── (autres fichiers)
    ```

??? question "Aurora affiche un mauvais artwork pour mon jeu"
    - Va dans la bibliothèque Aurora, sélectionne le jeu
    - Appuie sur le bouton **Y** (ou cherche dans les options du jeu)
    - Tu peux rechercher manuellement l'artwork ou le corriger via Unity (si connecté)

---

## Réseau & FTP

??? question "Quelle est l'IP de ma console ?"
    Dans Aurora : **Start > Paramètres système > Réseau**.
    Tu peux aussi utiliser **Advanced IP Scanner** depuis ton PC pour la détecter automatiquement.

??? question "FileZilla refuse la connexion"
    - Vérifie que la console est allumée et sur Aurora (ou que FTP DashLaunch est actif)
    - Identifiants par défaut : `xbox` / `xbox`, port `21`
    - Désactive temporairement ton antivirus/pare-feu pour tester

---

## Plugins

??? question "Comment savoir quels plugins sont compatibles avec ma version d'Aurora ?"
    Consulte la [page de compatibilité des plugins](plugins/compatibilite.md).
    En règle générale, les plugins développés pour Aurora 0.6b+ fonctionnent sur 0.7b.2.

??? question "Aurora freeze après l'installation d'un plugin"
    Connecte-toi en FTP depuis ton PC et supprime le plugin de `/Hdd1/Aurora/Plugins/`.
    Aurora redémarre normalement sans le plugin problématique.

---

## Tu ne trouves pas ta réponse ?

Si ta question n'est pas dans cette FAQ :

- Consulte le [glossaire](glossaire.md) pour les termes techniques
- Consulte les [forums de la scène](contribuer.md#ressources) (Logic Sunrise, RealModScene, se7enSins)
- [Ouvre une issue sur GitHub](https://github.com/TON_USERNAME/xbox360-aurora-guide/issues) pour suggérer d'ajouter ta question à la FAQ

!!! note "Contribuer à la FAQ"
    Tu as posé une question sur un forum et la réponse t'a été utile ?
    Propose-la ici via une [contribution](contribuer.md) !
