# SnowBrain - Formulaire de Cadrage Projet Logiciel

Formulaire HTML autonome pour collecter les informations client avant lancement d'un projet logiciel chez SnowBrain.

Le formulaire couvre le cadrage business, fonctionnel, technique, qualite, gouvernance, risques et budget, avec export exploitable dans Excel.

## Fonctionnalites

- Formulaire multi-sections complet (organisation, scope, exigences, integrations, planning, financier).
- Tableaux dynamiques (parties prenantes, backlog, integrations, jalons, risques).
- Sauvegarde automatique du brouillon en local (`localStorage`).
- Export Excel `.xlsx` (SheetJS local, sans dependance CDN).
- Export CSV compatible Excel en fallback.
- Meta SEO / Open Graph / Twitter + JSON-LD.
- Pack d'images SEO/social deja genere (`assets/seo`).

## Structure du projet

```text
formulaire-snowbrain.html
assets/
  seo/
    og-image-1200x630.png
    twitter-image-1200x600.png
    favicon-16x16.png
    favicon-32x32.png
    apple-touch-icon-180x180.png
    android-chrome-192x192.png
    android-chrome-512x512.png
    site.webmanifest
  vendor/
    xlsx.full.min.js
    xlsx.LICENSE.txt
```

## Lancer en local

Option simple: ouvrir `formulaire-snowbrain.html` dans le navigateur.

Option recommandee (serveur local):

```bash
python3 -m http.server 8080
```

Puis ouvrir:

```text
http://localhost:8080/formulaire-snowbrain.html
```

## Deploiement sur Vercel

Le projet est statique (pas de build obligatoire).

1. Pousser le repo sur GitHub.
2. Importer le repo dans Vercel.
3. Framework preset: `Other`.
4. Build command: vide.
5. Output directory: `.` (racine).

Vous pouvez servir le formulaire via:

```text
https://votre-domaine/formulaire-snowbrain.html
```

Le fichier `vercel.json` est deja inclus pour servir la page correctement sur `/` et eviter les 404 de redirection.

## Export Excel

- Le bouton **Exporter Excel (.xlsx)** utilise `assets/vendor/xlsx.full.min.js` en local.
- Si `XLSX` est indisponible, le formulaire bascule automatiquement en export CSV.

## Publication GitHub (si besoin)

```bash
git init
git branch -M main
git remote add origin git@github.com:DimitriTedom/SnowBrain---Formulaire-de-Cadrage-Projet-Logiciel.git
git add .
git commit -m "Initial project setup"
git push -u origin main
```

## Licence

Ce projet est publie sous licence MIT. Voir `LICENSE`.

Dependance tierce:
- `assets/vendor/xlsx.full.min.js` -> licence SheetJS dans `assets/vendor/xlsx.LICENSE.txt`.
