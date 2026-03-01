# TP 3.4 – Hooks et automatisation

Configurer des Git hooks avec Husky dans ce projet Node.js.

## Tâches

1. Installer Husky :
   ```bash
   npm install --save-dev husky
   npx husky init
   ```

2. Créer un hook **pre-commit** (`.husky/pre-commit`) :
   ```bash
   npm run lint
   ```

3. Optionnel — Configurer **commitlint** :
   ```bash
   npm install --save-dev @commitlint/cli @commitlint/config-conventional
   ```
   Créer `commitlint.config.js` :
   ```js
   module.exports = { extends: ['@commitlint/config-conventional'] };
   ```
   Créer `.husky/commit-msg` :
   ```
   npx --no -- commitlint --edit $1
   ```

4. Tester :
   - `git commit -m "bad message"` → doit **échouer** (si commitlint configuré)
   - `git commit -m "feat: add something"` → doit **passer**

## Résultat attendu

Un commit avec un message non conventionnel est bloqué automatiquement.
