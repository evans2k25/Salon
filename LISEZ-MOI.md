# Salon Prestige – paquet PWA

Contenu : `index.html` (application), `manifest.webmanifest`, `sw.js` (service worker), `icons/`.

## 1. Mettre en ligne (gratuit)
Choisissez un hébergeur HTTPS (obligatoire pour une PWA) :
- **Netlify** : netlify.com/drop → glissez-déposez le dossier décompressé. Vous obtenez une adresse en https://…netlify.app.
- **Cloudflare Pages** ou **Vercel** : même principe, ou connexion à un dépôt GitHub.
- **GitHub Pages** : déposez les fichiers dans un dépôt et activez Pages.
Tous les fichiers doivent rester à la racine du site, avec le dossier `icons/`.

## 2. Installer sur Android
1. Ouvrez l’adresse dans **Chrome** sur le téléphone.
2. Menu ⋮ → **Installer l’application** (ou « Ajouter à l’écran d’accueil »).
3. L’icône apparaît sur l’écran d’accueil, l’application s’ouvre en plein écran.
Astuce : générez un QR code de l’adresse et affichez-le au salon.

## 3. Personnaliser avant de publier
- Nom du salon : dans `index.html` (titre `<h1>` et `<title>`) et dans `manifest.webmanifest`.
- Prestations, horaires, équipe : onglet **Gestion** (code de démonstration 1234, à remplacer).
- Devise : variable `CUR` au début du script.
- Icônes : remplacez les 3 fichiers de `icons/` par le logo du salon (192, 512 et 512 « maskable »).

## 4. Mises à jour
Après chaque modification d’`index.html`, changez `VERSION` dans `sw.js` (ex. `v2`) pour que les téléphones récupèrent la nouvelle version.

## 5. Limites actuelles de ce paquet
- Les rendez-vous et réglages sont enregistrés **dans le navigateur de chaque appareil** : le téléphone du coiffeur ne voit pas les réservations faites depuis un autre téléphone.
- Pas de rappels SMS/WhatsApp.
- Le code gérant (1234) est écrit dans la page : il ne protège rien en production.
→ Étape suivante : base de données partagée (ex. Supabase), vraie connexion pour le gérant, rappels automatiques.

## 6. Play Store (facultatif, plus tard)
Une fois la PWA en ligne, **PWABuilder.com** (ou Bubblewrap) génère un fichier `.aab` à envoyer sur Google Play Console.
