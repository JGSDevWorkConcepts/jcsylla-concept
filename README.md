# Site web — Sylla JC Concept

Site vitrine statique (HTML/CSS/JS, sans framework) prêt pour GitHub Pages avec le domaine **jcsylla-concept.ch** (Infomaniak).

## Contenu

- `index.html` — site principal : conseil financier & fiscal (100 % à distance)
- `creation-3d.html` — page secondaire : création 3D (portfolio à venir sur ArtStation/Patreon)
- `finance.html` — simple redirection vers index.html (ancienne adresse)
- `docs/liste-documents-declaration-impot.pdf` — checklist téléchargeable
- `docs/conditions-generales.pdf` — conditions générales (for juridique : Montreux, droit suisse) — **à faire valider par un juriste**
- `assets/logo.svg` / `logo-blanc.svg` / `logo-mark.svg` / `logo-mark-blanc.svg` — logo vectoriel (textes en tracés, ouvrable dans Adobe Illustrator)
- `css/styles.css`, `js/main.js`, `assets/portrait.jpg`, `assets/favicon.png`
- `CNAME` — nécessaire pour le domaine personnalisé sur GitHub Pages

## 1. Créer le dépôt avec GitHub Desktop (compte JGSDevWorkConcepts)

1. GitHub Desktop → **File → New repository…**
   - Name : `jcsylla-concept`
   - Local path : un dossier de travail (p. ex. `E:\Dev\org\`)
   - → **Create repository**
2. Copier **tout le contenu** du dossier `site/` (index.html, creation-3d.html, finance.html, CNAME, css/, js/, assets/, docs/) **à la racine** du nouveau dépôt local — pas dans un sous-dossier `site/`.
3. GitHub Desktop affiche les fichiers dans « Changes » → message de commit (p. ex. `Site initial`) → **Commit to main**.
4. **Publish repository** → Organization : `JGSDevWorkConcepts` → **décocher « Keep this code private »** (GitHub Pages gratuit exige un dépôt public) → Publish.

## 2. Activer GitHub Pages

1. Sur github.com : dépôt `JGSDevWorkConcepts/jcsylla-concept` → **Settings → Pages**.
2. Source : « Deploy from a branch » → branche `main`, dossier `/ (root)` → **Save**.
3. Après ~1 minute : site visible sur `https://jgsdevworkconcepts.github.io/jcsylla-concept/`.

## 3. Lier le domaine jcsylla-concept.ch (Infomaniak)

1. **Settings → Pages → Custom domain** : saisir `jcsylla-concept.ch` → Save (le fichier `CNAME` du dépôt correspond déjà).
2. Manager Infomaniak → Domaine `jcsylla-concept.ch` → **Zone DNS** :

   | Type  | Nom (source) | Valeur (cible)                 |
   |-------|--------------|--------------------------------|
   | A     | @            | 185.199.108.153                |
   | A     | @            | 185.199.109.153                |
   | A     | @            | 185.199.110.153                |
   | A     | @            | 185.199.111.153                |
   | CNAME | www          | jgsdevworkconcepts.github.io   |

   Supprimer les anciens enregistrements A / AAAA sur `@` (ceux d'Infomaniak web).
   **Ne pas toucher aux enregistrements MX** : ils gèrent l'e-mail info@jcsylla-concept.ch.
3. Propagation DNS : de quelques minutes à 24 h.
4. Retour dans **Settings → Pages** : « Check again » si besoin, puis cocher **Enforce HTTPS**.

## 4. Workflow quotidien (VSCode + GitHub Desktop)

1. GitHub Desktop → **Repository → Open in Visual Studio Code**.
2. Modifier les fichiers dans VSCode, sauvegarder.
3. GitHub Desktop (ou l'onglet Source Control de VSCode) : commit → **Push origin**.
4. Le site est redéployé automatiquement ~1 minute après chaque push.

## Notes

- Les prix affichés : déclaration d'impôt CHF 165.– / avec optimisation CHF 270.–. Le reste est « sur devis ».
- Le logo actuel (`assets/logo.png`) est la v3 — remplacer ce fichier suffit pour le mettre à jour partout.
- Quand la galerie 3D sera en ligne, remplacer le bloc « Bientôt en ligne » dans `creation-3d.html` par un lien vers celle-ci.