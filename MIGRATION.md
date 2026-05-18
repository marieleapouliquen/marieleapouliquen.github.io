# Guide de migration WordPress → GitHub Pages

Ce document récapitule les choix faits et liste les étapes à compléter de ton côté.

## ✅ Ce qui est déjà fait

### Structure et thème
- Thème Jekyll allégé sur mesure (inspiré d'al-folio mais épuré)
- Style noir & blanc, typographie EB Garamond + Inter
- Sidebar minimaliste (photo + nom + statut + liens)
- Header avec navigation horizontale
- Footer sobre
- Responsive (mobile + desktop)

### Contenu rédigé
- **Accueil** — pitch d'introduction + 3 cartes + bloc actualités
- **Recherche** — projet Cap Nature complet
- **Enseignement** — historique complet (Univ. Rennes, SYA, ISE...)
- **Publications** — article Remote Sensing + 4 mémoires/rapports
- **Diffusion** — IFA, Terra Klima, EnviroSYA, AMS, Cornell
- **CV** — formation, expérience, certifications
- **À propos** — parcours détaillé + lien MLYK's Corner
- **English** — version courte anglaise

### Actualités (exemples)
- Publication Remote Sensing (2022)
- Cornell Lab retreat (2023)
- Début de thèse (2024)
- Conférence IFA (déc. 2024)

Tu peux supprimer/modifier ces actualités, elles sont juste là pour illustrer.

## 📌 À faire de ton côté

### Avant la première publication

1. **Choisir le nom de dépôt GitHub** : créer un dépôt nommé `USERNAME.github.io`
2. **Remplacer `USERNAME` dans `_config.yml`** ligne `url:` par ton vrai nom d'utilisateur
3. **Uploader ta photo de profil** : déposer une image carrée dans `assets/img/profile.jpg`
   - Recommandation : photo terrain ou atelier, ~500×500 px, format JPG
4. **Créer ton compte ORCID** (gratuit, indispensable) : [orcid.org](https://orcid.org)
   - Une fois l'ID obtenu, décommente la ligne `orcid:` dans `_config.yml`
5. **Créer un Google Scholar** (gratuit, recommandé) : [scholar.google.com](https://scholar.google.com)
   - Ajoute l'identifiant à `_config.yml`

### Après la première publication

6. **Vérifier toutes les pages** en local (`bundle exec jekyll serve`) avant de pousser
7. **Adapter les images** : pour chaque page, tu peux ajouter des images via Markdown :
   ```markdown
   ![Légende]({{ '/assets/img/nom-image.jpg' | relative_url }})
   ```
8. **Ajouter ton CV en PDF** dans `assets/pdf/cv-mlpouliquen-2026.pdf` puis lier dans `_pages/cv.md`
9. **Activer le domaine personnalisé** `marieleapouliquen.com` une fois que tu valides le site

### Choses à ajouter au fil du temps

- Photos en pleine page sur Recherche, Diffusion (atelier CapNature, conférence IFA, etc.)
- Liens vers les ressources Terra Klima en ligne (quand elles seront hébergées)
- Section "Communications" sur la page Recherche (au fil des colloques)
- Page "Climat et DEF" (syllabus du cours L2/L3) — peut être ajoutée comme sous-page de Enseignement

## 🔄 Comparaison WordPress → Jekyll

| Action | WordPress | Jekyll |
|---|---|---|
| Modifier une page | Admin → Pages → Elementor | Éditer le fichier `.md` |
| Ajouter une publication | Elementor → glisser-déposer | Ajouter un bloc dans `publications.md` |
| Changer le menu | Apparence → Menus | Éditer `_data/navigation.yml` |
| Changer une couleur | Personnaliser → Couleurs | Éditer `assets/css/main.css` |
| Mettre en ligne | Automatique | `git push` |
| Sauvegarder | Plugin UpdraftPlus | L'historique git **est** la sauvegarde |

## 🎯 Tests à faire avant de migrer ton domaine

1. Vérifier toutes les pages en mode bureau ET mobile
2. Cliquer sur tous les liens (internes et externes)
3. Vérifier le rendu sur Safari, Chrome, Firefox
4. Tester l'envoi d'e-mail via les liens `mailto:`
5. Vérifier le sitemap : `https://USERNAME.github.io/sitemap.xml`

## ⚠️ Différences importantes par rapport à WordPress

- **Pas d'interface de personnalisation visuelle** : tout passe par l'édition de fichiers texte. C'est plus rapide quand on sait, plus déroutant au début.
- **Pas de plugins** : pas de Elementor, pas d'analytics WordPress. Pour Google Analytics, ajoute juste le tag dans `_layouts/default.html`.
- **Pas de commentaires** : si tu veux un blog avec commentaires, il faut ajouter un service externe (Disqus, Giscus...). Pas nécessaire pour un site académique.
- **Sécurité** : aucun risque de piratage WordPress, tout est statique.

## 📞 Si tu bloques

Pour toute question :
- Documentation Jekyll : [jekyllrb.com/docs](https://jekyllrb.com/docs/)
- Sur Git : [Pro Git Book](https://git-scm.com/book/fr/v2)
- Sur Markdown : [commonmark.org/help](https://commonmark.org/help/)
