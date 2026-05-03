# 📖 Guide Aurora FR 2026

> Documentation francophone moderne pour Xbox 360 JTAG/RGH sous Aurora Dashboard.

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen?logo=github)](https://ElMajoR9.github.io/xbox360-aurora-guide/)
[![Licence CC BY-SA 4.0](https://img.shields.io/badge/Licence-CC%20BY--SA%204.0-lightgrey)](https://creativecommons.org/licenses/by-sa/4.0/deed.fr)
[![Contributions bienvenues](https://img.shields.io/badge/Contributions-bienvenues-blue)](CONTRIBUTING.md)

---

## 🌐 Lire le guide

**→ [ElMajoR9.github.io/xbox360-aurora-guide](https://ElMajoR9.github.io/xbox360-aurora-guide/)**

---

## À propos

Ce guide vise à centraliser et moderniser toute la documentation francophone sur l'utilisation
d'une Xbox 360 moddée (JTAG/RGH) sous Aurora Dashboard en 2026.

La documentation disponible sur les forums date de 2012-2016, est dispersée et parfois incorrecte.
Ce projet cherche à créer une référence unique, claire, maintenue et ouverte aux contributions.

### Ce que couvre le guide

- ✅ Installation d'Aurora Dashboard
- ✅ Configuration de DashLaunch
- ✅ Réseau et FTP (accès depuis le PC)
- ✅ Gestion des plugins Aurora
- ✅ Personnalisation (thèmes, skins)
- ✅ Outils PC recommandés
- ✅ FAQ complète
- ✅ Glossaire du jargon homebrew

### Ce que ce guide ne couvre PAS

Ce guide est entièrement dédié au homebrew légal, à la personnalisation et à la préservation.
Il n'aborde pas le piratage, la triche en ligne, la manipulation du Xbox Live ou la distribution
de contenu protégé.

---

## 🤝 Contribuer

Toutes les contributions sont bienvenues !

- **Corriger une erreur** : Clique sur ✏️ sur n'importe quelle page du site
- **Signaler un problème** : [Ouvre une issue](../../issues)
- **Proposer une section** : [CONTRIBUTING.md](CONTRIBUTING.md)

Tu n'as pas besoin d'être développeur pour contribuer. Si tu connais Aurora, tu peux contribuer.

---

## 🛠️ Développement local

```bash
# Installer MkDocs Material
pip install mkdocs-material

# Lancer le serveur de prévisualisation local
mkdocs serve

# Le site est accessible sur http://127.0.0.1:8000
```

---

## 📁 Structure du projet

```
xbox360-aurora-guide/
├── docs/
│   ├── index.md                    ← Page d'accueil
│   ├── installation/
│   │   ├── aurora.md               ← Installer Aurora
│   │   ├── dashlaunch.md           ← Configurer DashLaunch
│   │   └── reseau.md               ← Réseau et FTP
│   ├── plugins/
│   │   ├── installation.md         ← Installer un plugin
│   │   └── compatibilite.md        ← Liste de compatibilité
│   ├── personnalisation/
│   │   └── themes.md               ← Thèmes Aurora
│   ├── outils-pc/
│   │   └── index.md                ← Outils PC recommandés
│   ├── faq.md                      ← FAQ
│   ├── glossaire.md                ← Glossaire
│   └── contribuer.md               ← Comment contribuer
├── .github/
│   └── workflows/
│       └── deploy.yml              ← Déploiement automatique GitHub Pages
├── mkdocs.yml                      ← Configuration MkDocs
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## 📄 Licence

Contenu sous licence [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.fr).
Libre de partager et d'adapter avec attribution et sous la même licence.
