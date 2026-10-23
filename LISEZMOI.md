# Planif Muscu : version autonome

Appli web sans compte ni serveur, qui fonctionne hors ligne une fois installée.
Les données restent sur l'appareil, dans le stockage du navigateur.

## Contenu
- `index.html` : l'appli complète, avec la bibliothèque de 161 exercices intégrée
- `vbt.html` : outil de mesure de vitesse à la caméra (option du mode séance)
- `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png` : installation sur l'écran d'accueil et fonctionnement hors ligne

## Mise en ligne (une seule fois, gratuit)
L'installation sur téléphone exige une adresse https. Deux options :

**GitHub Pages**
1. Créer un dépôt, par exemple `planif-muscu`, et y déposer les 5 fichiers à la racine.
2. Aller dans Settings › Pages › Branch : `main` / `root` › Save.
3. L'appli est disponible à l'adresse `https://<utilisateur>.github.io/planif-muscu/`.

**Netlify ou Cloudflare Pages** : glisser-déposer le dossier sur app.netlify.com/drop ou sur Cloudflare Pages.

## Installation sur le téléphone
1. Ouvrir l'adresse dans Safari (iPhone) ou Chrome (Android).
2. iPhone : Partager › « Sur l'écran d'accueil ». Android : menu ⋮ › « Installer l'application ».
3. L'icône ouvre directement le **mode séance**. Ensuite, l'appli fonctionne sans réseau.

## Données et sauvegardes
- Tout est enregistré automatiquement sur l'appareil.
- **Sauvegarder** télécharge un fichier `.json` contenant les programmes, les séances réalisées et les exercices perso.
- **Restaurer** recharge ce fichier. Les données sont fusionnées : la version la plus récente de chaque programme est conservée.
- Pour passer du PC au téléphone, sauvegarder sur l'un et restaurer sur l'autre, via un cloud ou une messagerie par exemple.
- Faire une sauvegarde régulière. Effacer les données du navigateur supprime tout.

## Option : vitesse à la caméra (VBT)

Option désactivée par défaut. En mode séance, touchez **📷 Vitesse** en haut pour l'activer ou la désactiver (réglage propre à ce téléphone). Une fois activée, chaque série a un bouton 📷 :

1. Touchez 📷 sur la série : l'outil caméra s'ouvre (fichier `vbt.html`, le même moteur que Vitesse Barre ; cible et calibrage sont mémorisés d'une fois sur l'autre).
2. « Démarrer la série », faites vos reps ; la série s'arrête seule après quelques secondes d'immobilité.
3. « Valider dans la séance » : le nombre de reps est rempli, la série est cochée, la charge prévue est reprise si vous ne l'avez pas saisie. Le RPE reste à saisir.

Sous la série s'affichent : vitesse moyenne (moyenne des vitesses moyennes concentriques des reps), meilleure et dernière rep, **%Vdec = (meilleure − dernière) ÷ meilleure**, et la vitesse de chaque rep. Le résumé de séance ajoute une colonne vitesse · %Vdec. L'export CSV ajoute : reps caméra, V moy, V meilleure, V première, V dernière, %Vdec, score Vdec (1 − moyenne ÷ meilleure), et les vitesses moyennes, maximales et amplitudes rep par rep.

Vous pouvez toujours corriger le nombre de reps à la main après la mesure.

## Mise à jour de l'appli
Remplacer `index.html` en ligne. Pour forcer le rechargement chez tous les utilisateurs, augmenter le numéro de version (`planif-muscu-v8` → `v9`…) dans `sw.js`.
