# Workflow de production – 15 minutes chrono

Ce fichier décrit le process complet pour (re)générer le pack en 15 minutes.

## Minute 0–3 : Téléchargement & sélection

1. Cloner ou mettre à jour le repo open‑source :
   - Repo : `jankapunkt/latexcv`
   - URL : https://github.com/jankapunkt/latexcv
2. Récupérer les PDF compilés des templates (classic, modern, infographics, sidebar, rows, two_column).
3. Copier les PDF sélectionnés dans `templates-pdf/originaux/`.

## Minute 3–8 : Personnalisation (Canva)

1. Importer les PDFs dans Canva (outil "Modifier un PDF").
2. Créer 2 à 3 variations de couleurs par template :
   - Bleu Corporate (#2563EB)
   - Vert Émeraude (#059669)
   - Rouge Bordeaux (#991B1B)
3. Exporter chaque variation en PDF haute qualité dans `templates-pdf/variations/`.

## Minute 8–11 : Conversion en fichiers modifiables

1. Aller sur CloudConvert ou équivalent.
2. Convertir les PDFs finaux en `.docx`.
3. Sauvegarder dans `templates-docx/` et vérifier l’alignement texte.

## Minute 11–13 : Création des assets marketing

1. Ouvrir Canva → utiliser un template de cover ebook / produit digital.
2. Créer :
   - `assets/cover.png` (visuel principal Gumroad)
   - `assets/mockup-grid.png` (grille de plusieurs CV)
   - `assets/guide-preview.png` (aperçu du guide)
3. Exporter en PNG.

## Minute 13–15 : Upload Gumroad & configuration

1. Zipper le contenu :
   - `templates-pdf/`
   - `templates-docx/`
   - `guide/`
   - `prompts/`
2. Aller sur Gumroad → New Product.
3. Uploader le ZIP + les images `assets/*.png`.
4. Copier‑coller la fiche produit depuis `gumroad/product_page.md`.
5. Régler le prix à **€14,99** et publier.
