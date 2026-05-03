# Guide de contribution

Merci de vouloir contribuer au Guide Aurora FR 2026 ! Ce document explique comment le faire efficacement.

## Prérequis

Tu n'as besoin que d'un compte GitHub. Pas de compétences techniques particulières requises.

## Modifier une page existante

1. Va sur [le site du guide](https://TON_USERNAME.github.io/xbox360-aurora-guide/)
2. Navigue vers la page à modifier
3. Clique sur l'icône ✏️ en haut à droite de la page
4. GitHub ouvre l'éditeur directement dans le navigateur
5. Fais tes modifications
6. En bas de page, clique sur **"Propose changes"**
7. Décris brièvement ce que tu as changé et pourquoi
8. Clique sur **"Create pull request"**

## Ajouter une nouvelle page

1. Fork le dépôt (bouton "Fork" en haut à droite sur GitHub)
2. Dans ton fork, crée un nouveau fichier `.md` dans le bon dossier sous `docs/`
3. Ajoute la page dans `mkdocs.yml` sous la bonne section du menu `nav:`
4. Soumets une Pull Request

## Conventions de rédaction

- Rédige en **français clair et direct**
- Utilise le **vouvoiement → tutoiement** : le guide tutoie le lecteur (cohérent avec le reste)
- Privilégie les listes et tableaux pour les informations structurées
- Utilise les blocs `!!! tip`, `!!! warning`, `!!! info` pour mettre en avant des informations importantes
- Indique toujours quand une section est incomplète avec `!!! note "Section en construction"`

## Format des blocs Markdown courants

```markdown
!!! tip "Conseil"
    Texte du conseil ici.

!!! warning "Attention"
    Texte d'avertissement ici.

!!! info "Info"
    Information complémentaire ici.

??? question "Question pliée"
    Réponse visible au clic.
```

## Ce qu'on n'accepte pas

- Contenu facilitant le piratage ou le contournement de DRM
- Contenu lié au Xbox Live sur console modifiée
- Copie de contenu sans source et sans autorisation
- Promotion commerciale

## Questions ?

Ouvre une [issue](../../issues) avec le tag `question`.
