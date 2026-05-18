# Site académique — Marie-Léa Pouliquen

Site personnel construit avec **Jekyll** et hébergé sur **GitHub Pages**.
Style : noir & blanc, typographie EB Garamond (titres) + Inter (texte courant).

## 🚀 Démarrage rapide

### 1. Installer Ruby & Jekyll (macOS)

```bash
# Si Homebrew n'est pas installé :
# /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

brew install ruby
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

gem install --user-install bundler jekyll
```

### 2. Cloner et lancer en local

```bash
cd path/to/this/folder
bundle install
bundle exec jekyll serve
```

Ouvre [http://127.0.0.1:4000](http://127.0.0.1:4000) — le site s'affiche en local.
Le serveur recompile automatiquement à chaque modification.

### 3. Publier sur GitHub Pages

1. Créer un nouveau dépôt GitHub nommé exactement **`USERNAME.github.io`** (où `USERNAME` est ton nom d'utilisateur GitHub).
2. Initialiser git dans ce dossier et pousser :

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/USERNAME/USERNAME.github.io.git
git push -u origin main
```

3. Dans **Settings → Pages** du dépôt, vérifier que la source est `main` / `(root)`.
4. Le site est en ligne à `https://USERNAME.github.io` dans les 1-2 minutes.

### 4. Pointer ton domaine `marieleapouliquen.com` (plus tard)

Une fois que tu es satisfaite du résultat, voir la documentation officielle :
[docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

## 📂 Structure du projet

```
.
├── _config.yml          → Configuration générale (titre, auteur, liens)
├── _data/
│   └── navigation.yml   → Menu principal du site
├── _includes/           → Fragments HTML réutilisables
├── _layouts/
│   ├── default.html     → Template principal de toutes les pages
│   └── home.html        → Template de l'accueil
├── _news/               → Actualités (1 fichier par actualité)
├── _pages/              → Toutes les pages du site
│   ├── index.md         → Accueil
│   ├── recherche.md
│   ├── enseignement.md
│   ├── publications.md
│   ├── diffusion.md
│   ├── cv.md
│   ├── about.md
│   └── english.md
├── assets/
│   ├── css/
│   │   └── main.css     → Feuille de style (à modifier pour ajuster le design)
│   ├── img/             → Toutes les images (mettre profile.jpg ici)
│   └── pdf/             → CV PDF et autres documents
├── Gemfile              → Dépendances Ruby
└── README.md
```

## ✏️ Comment modifier le contenu

### Modifier une page existante

Ouvre le fichier `.md` correspondant dans `_pages/`, modifie le texte (en Markdown), enregistre.
Le serveur local recompile automatiquement.

### Ajouter une actualité

Crée un fichier dans `_news/` au format `YYYY-MM-DD-titre.md` :

```markdown
---
date: 2026-06-15
---
Présentation orale au colloque XYZ à Bordeaux.
```

L'actualité apparaîtra automatiquement sur la page d'accueil, triée chronologiquement.

### Ajouter une publication

Édite `_pages/publications.md` et ajoute un bloc `<div class="publication">` en suivant le format existant.

### Changer la photo de profil

Remplace `assets/img/profile.jpg` par ta photo (carrée idéalement, ~500×500 px).

### Ajouter ORCID, Google Scholar, HAL, etc.

Édite `_config.yml`, section `social:` — décommente et remplis les lignes correspondantes.
Les liens apparaissent automatiquement dans la sidebar.

## 🎨 Ajuster le design

Toute la mise en forme est dans `assets/css/main.css`.
Les variables principales sont en haut du fichier (`:root`) :

```css
--color-text: #111111;
--color-bg: #ffffff;
--font-serif: 'EB Garamond';
--font-sans: 'Inter';
--max-width: 1200px;
--sidebar-width: 240px;
```

## 🔧 Commandes utiles

```bash
# Démarrer le serveur local
bundle exec jekyll serve

# Forcer une régénération complète
bundle exec jekyll build --trace

# Mettre à jour les dépendances
bundle update
```

## 📚 Ressources

- Documentation Jekyll : [jekyllrb.com/docs](https://jekyllrb.com/docs/)
- Markdown : [commonmark.org/help](https://commonmark.org/help/)
- GitHub Pages : [pages.github.com](https://pages.github.com/)

---

Voir aussi [MIGRATION.md](./MIGRATION.md) pour les détails de la migration depuis WordPress.
