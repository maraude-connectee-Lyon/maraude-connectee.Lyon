# La Maraude connectée — paquet prêt pour GitHub

Ce paquet contient l'interface HTML et les fichiers de structure de données de **La Maraude connectée**.

## Contenu

- `index.html` : interface web complète, autonome côté navigateur.
- `README.md` : guide de déploiement et limites connues.
- `data/maraude_connectee.db` : base SQLite de départ.
- `data/schema.sql` : schéma SQL de référence pour les ressources, réglages, actualités, alertes et phrases.
- `data/schema-quick-links.sql` : schéma SQL minimal des liens rapides.
- `data/taxonomie.json` : métadonnées et description des derniers ajouts.
- `.nojekyll` : indique à GitHub Pages de ne pas appliquer Jekyll.

## Dernières modifications présentes dans `index.html`

- « Accès à une borne de recharge » après « Accès à la santé », dans « + de droits ».
- Lien vers Autour d'ici avec paramètres de localisation de Lyon.
- Rubrique « Échanger dans une autre langue » avec une icône SVG représentant deux bulles de dialogue.

## Prévisualisation locale

Ouvrir `index.html` dans un navigateur récent. Pour un test local via serveur HTTP, lancer dans le dossier du paquet :

```bash
python -m http.server 8000
```

Puis ouvrir `http://localhost:8000`.

## Publication gratuite sur GitHub Pages

1. Créer ou ouvrir le dépôt GitHub.
2. Importer **tout le contenu** de ce dossier à la racine du dépôt, de façon à avoir `index.html` à la racine.
3. Dans GitHub : **Settings → Pages**.
4. Choisir **Deploy from a branch**, sélectionner `main` et le dossier `/ (root)`, puis enregistrer.
5. Attendre la fin du déploiement et ouvrir l'URL GitHub Pages affichée dans les paramètres.

GitHub Pages héberge les fichiers statiques. Il n'exécute pas de serveur PHP/Node et n'héberge pas une base SQLite active.

## Important : base de données et espace administrateur

Le fichier `maraude_connectee.db` et `schema.sql` constituent une base de départ, mais **l'interface HTML n'est pas automatiquement connectée à cette base**. Pour publier des actualités visibles par tous, synchroniser des alertes, enregistrer les modifications d'un administrateur ou partager des données entre téléphones, il faut un backend/API et une base hébergée, avec authentification et règles de sécurité. Ne pas placer de mots de passe ou de secrets dans `index.html` ni dans un dépôt public.

## Vérifications à faire avant diffusion

- Tester les liens externes sur smartphone.
- Vérifier que le site Autour d'ici accepte les paramètres de localisation; si ce n'est pas le cas, il peut s'ouvrir sans être centré sur Lyon.
- Vérifier les parcours d'accueil, urgences, alertes, langues et À propos.
- Vérifier les informations et coordonnées des structures avant une diffusion publique.

## Version

Version affichée dans l'application : `1.0.0`. Révision de ce paquet : `2026-10-15`.
