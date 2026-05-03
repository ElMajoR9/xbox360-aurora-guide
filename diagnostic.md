# Diagnostic et dépannage

Cette page recense les problèmes les plus fréquents rencontrés sur une Xbox 360 JTAG/RGH sous Aurora,
avec leurs causes et solutions.

---

## Problèmes de démarrage

### La console ne démarre pas sur Aurora

**Symptôme :** La console démarre sur le NXE (dashboard Microsoft) ou sur un écran noir.

**Causes possibles :**
- `defaultapp` mal configuré dans DashLaunch
- Fichier `Aurora.xex` manquant ou corrompu
- DashLaunch non installé

**Solutions :**
1. Lance l'`Installer.xex` de DashLaunch depuis une clé USB
2. Vérifie que `defaultapp = Hdd1:\Aurora\Aurora.xex` est correctement renseigné
3. Vérifie que `Aurora.xex` est bien présent sur le disque dur
4. Si Aurora est corrompu, réinstalle-le via clé USB

---

### La console freeze pendant le démarrage de RGH

**Symptôme :** Le logo Xbox s'affiche puis la console freeze ou redémarre en boucle.

**Causes possibles :**
- Comportement normal du RGH — le glitch rate et la console redémarre pour réessayer
- Sur RGH 1.0, plusieurs tentatives sont normales avant un démarrage réussi

**Solutions :**
- Sur RGH 1.0 : attends patiemment, c'est normal (jusqu'à 30-60 secondes parfois)
- Sur RGH 2.0 / 3.0 : si ça prend plus de 2 minutes, il peut y avoir un problème matériel
- Vérifie les connexions des fils du chip de modification

---

### Écran rouge (RROD) au démarrage

**Symptôme :** 3 ou 4 secteurs de l'anneau lumineux sont rouges.

!!! danger "Attention"
    Le RROD (Red Ring of Death) indique une panne matérielle sérieuse.
    Ce guide ne couvre pas la réparation matérielle. Consulte un spécialiste ou les forums dédiés
    (RealModScene, se7enSins) pour diagnostiquer le code d'erreur exact.

**Code d'erreur :** Compte les clignotements de l'anneau pour identifier le code (E74, E68, etc.)
et recherche-le sur les forums spécialisés.

---

## Problèmes avec Aurora

### Aurora crash ou freeze

**Symptôme :** Aurora se fige ou se ferme brutalement.

**Solutions :**
1. Désactive les plugins un par un pour identifier le coupable
2. Supprime le cache Aurora : `Hdd1:/Aurora/Data/cache/`
3. Supprime et recrée `settings.db` (tu perdras tes paramètres)
4. Réinstalle Aurora proprement

---

### La bibliothèque de jeux est vide

**Symptôme :** Aurora démarre mais n'affiche aucun jeu.

**Solutions :**
1. Va dans **Paramètres > Gestion des sources** et vérifie les chemins
2. Lance un scan manuel
3. Vérifie que tes jeux ont bien un fichier `default.xex` à leur racine
4. Vérifie que les permissions FTP permettent l'accès aux dossiers concernés

---

### Les artworks ne se chargent pas

**Symptôme :** Les jeux s'affichent sans image de couverture.

**Solutions :**
1. Vérifie que la console est connectée au réseau
2. Dans Aurora, vérifie la configuration d'Unity (service de métadonnées)
3. Lance une récupération manuelle d'artwork (touche Y sur le jeu)
4. Supprime le cache d'artworks : `Hdd1:/Aurora/Data/cache/`

---

## Problèmes réseau et FTP

### Impossible de se connecter en FTP

**Symptôme :** FileZilla affiche "Connexion refusée" ou timeout.

**Checklist :**
- [ ] La console est allumée et sur Aurora (ou FTP DashLaunch actif)
- [ ] La console est bien connectée au réseau (câble ou Wi-Fi)
- [ ] Tu utilises la bonne IP (elle peut changer si DHCP)
- [ ] Les identifiants sont corrects (`xbox` / `xbox` par défaut)
- [ ] Le port FTP n'est pas bloqué par ton pare-feu Windows
- [ ] Le plugin FTP est actif dans Aurora (Paramètres > Plugins)

**Test rapide :** Essaie de pinguer la console depuis ton PC :
```
ping 192.168.1.XX    ← remplace par l'IP de ta console
```
Si le ping ne répond pas, c'est un problème réseau, pas FTP.

---

### La connexion FTP se coupe pendant un transfert

**Causes et solutions :**
- **Réseau Wi-Fi instable** → utilise un câble Ethernet
- **Timeout FileZilla** → dans FileZilla : Édition > Paramètres > Connexion > augmente le timeout à 60s
- **Fichier trop volumineux** → transfère les gros fichiers en plusieurs fois

---

## Problèmes de jeux

### Un jeu refuse de se lancer

**Symptôme :** Le jeu est dans la bibliothèque Aurora mais crash ou affiche une erreur au lancement.

**Solutions :**
1. Vérifie que le fichier `default.xex` est intact (taille non nulle)
2. Certains jeux nécessitent un patch de région ou de titre — cherche sur les forums
3. Vérifie la compatibilité du jeu avec ton kernel (certains titres demandent un kernel spécifique)
4. Essaie avec et sans les plugins Aurora actifs (conflit possible)

---

### Le jeu se lance mais freeze en cours de partie

**Causes possibles :**
- Fichiers du jeu corrompus ou incomplets
- Disque dur défaillant
- Surchauffe de la console

**Solutions :**
1. Vérifie la température de la console (utilitaire Temperature Monitor)
2. Assure-toi que la ventilation est correcte (console non enfermée)
3. Teste avec un autre jeu pour isoler le problème
4. Si c'est systématique, le disque dur peut être défaillant

---

## Diagnostic thermique

### Vérifier les températures

La Xbox 360 est connue pour ses problèmes de chauffe.

**Signes de surchauffe :**
- Ventilateurs qui s'emballent au bout de quelques minutes
- Console qui s'éteint toute seule
- Image qui se dégrade (artefacts visuels)
- RROD

**Bonnes pratiques :**
- Assure-toi que les grilles de ventilation (droite et arrière) sont dégagées
- Ne pose pas la console dans un meuble fermé
- Nettoie régulièrement la poussière (soufflette)
- Remplace la pâte thermique si la console a plusieurs années (opération matérielle avancée)

---

## Logs Aurora

En cas de problème difficile à diagnostiquer, les logs Aurora peuvent aider.

**Emplacement :** `Hdd1:/Aurora/Logs/Aurora.log`

**Comment y accéder :**
1. Connecte-toi en FTP
2. Navigue vers `Hdd1:/Aurora/Logs/`
3. Télécharge `Aurora.log` sur ton PC
4. Ouvre-le avec un éditeur de texte et cherche les lignes contenant `ERROR` ou `CRITICAL`

---

!!! note "Problème non listé ?"
    Si tu as résolu un problème non documenté ici, [partage ta solution](../contribuer.md) —
    elle aidera forcément d'autres utilisateurs.
