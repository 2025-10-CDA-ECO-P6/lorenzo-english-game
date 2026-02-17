# Brief 5 — English Game

## 1. Organisation du projet

- `index.html` : structure HTML principale.
- `assets/scss/` : styles SCSS modulaires.
  - `components/` : composants (`_navbar.scss`, `_hero.scss`, `_challenge.scss`, `_schedule.scss`, `_project.scss`, `_footer.scss`)
  - `vars/` : variables globales (`_variables.scss`)
  - `ui/` : typographie et règles UI
  - `mixins/` : mixins (vide pour l'instant)
- `assets/css/style.css` : CSS compilé (généré depuis `assets/scss/style.scss`).
- `assets/images/` : images utilisées.

## 2. Choix techniques

- SCSS modulaire : chaque composant possède son fichier `_component.scss` pour faciliter la maintenance et la réutilisabilité.
- Variables centralisées dans `assets/scss/vars/_variables.scss` pour couleurs, espacements et breakpoints.
- Pas de framework externe — CSS pur compilé depuis SCSS pour garder le contrôle total du design.
- Compilateur utilisé localement : `npx sass assets/scss/style.scss assets/css/style.css`.

## 3. Stratégie responsive

- Breakpoints utilisés : `$bp-tablet: 768px`, `$bp-desktop: 1024px`.
- Mobile-first : styles de base pour mobile, puis `@media (min-width: $bp-tablet)` pour ajustements desktop.
- Layouts :
  - `challenge` et `project` passent en grid 3 colonnes sur desktop (`max-width: 1100px`).
  - `schedule` affiche une version compacte (card) sur mobile et une image/visuel plus large sur desktop.
- Comportements : visibilité contrôlée via règles SCSS (ex : `.schedule__card` masquée sur desktop).

### Commandes utiles

- Compiler SCSS → CSS :

```bash
npm run sass
```

- Ouvrir le `index.html` dans un navigateur ou utiliser un serveur local (Live Server / http-server) pour voir le rendu.

Si tu veux, je peux :

- extraire des mixins et réduire la duplication SCSS,
- ajouter des classes utilitaires pour les accents (ex : `.accent--orange`) au lieu d'utiliser `nth-child`,
- améliorer l'accessibilité et ajouter des attributs ARIA.
