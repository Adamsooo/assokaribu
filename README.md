````md
# Karibu UGE – Site vitrine (1ʳᵉ tentative avec Vue.js)

Ce projet visait à créer une première version du site web vitrine de l'association **Karibu UGE**, dans le cadre de l’apprentissage du développement frontend avec **Vue.js** et **Tailwind CSS**.

---

## 🛠️ Technologies utilisées

- **Vite** (initialisation rapide du projet)
- **Vue 3** (composition API, SPA)
- **Vue Router** (navigation entre les pages)
- **Tailwind CSS** (design utilitaire)
- **PostCSS & Autoprefixer** (transformation CSS)
- **Git & GitHub** (versionnement)

---

## ✅ Étapes réalisées

### 1. Initialisation du projet
```bash
npm create vite@latest karibu-uge -- --template vue
npm install
````

Création d’une structure propre :

```
src/
├── assets/
├── components/
├── pages/
├── router/
```

### 2. Configuration de Tailwind CSS

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Ajout du contenu dans `tailwind.config.js` :

```js
export default {
  content: ["./index.html", "./src/**/*.{vue,js,ts,jsx,tsx}"],
  theme: { extend: {} },
  plugins: [],
}
```

Ajout du fichier `src/assets/main.css` :

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Import du fichier CSS dans `main.js` :

```js
import './assets/main.css'
```

### 3. Mise en place du routage

* Création de `router/index.js`
* Configuration de la route `/` vers `Home.vue`
* Intégration dans `main.js` via `.use(router)`

### 4. Création des premiers composants

* `Home.vue` avec un titre et un paragraphe
* Début de `App.vue` structuré avec `<router-view />`

---

## ❗ Problèmes rencontrés

### ❌ Problème majeur : Tailwind CSS non pris en compte

Malgré une installation correcte, le style par défaut de Vite persistait (police, couleurs de fond, etc.).

#### 🛠️ Débogage effectué :

* Suppression du fichier `style.css` par défaut
* Création manuelle du fichier `main.css` dans `src/assets/`
* Vérification du contenu `tailwind.config.js` et `postcss.config.js`
* Nettoyage du cache Vite (`rm -rf node_modules/.vite`)
* Redémarrage avec `npm run dev`

Finalement, même l’utilisation explicite de :

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

… à la place de `@import "tailwindcss";` semble ne pas fonctionner.

---

## 📌 Bilan

Le projet a permis :

* Une bonne familiarisation avec l’écosystème Vue + Tailwind
* La structuration propre d’un projet SPA
* L’apprentissage des bonnes pratiques de configuration

### 🔁 Prochaine étape :

Refonder le projet à partir de zéro, potentiellement avec **React**.

---

## 💡 À venir (dans le prochain projet)

* Meilleure intégration visuelle dès le départ
* Création de tous les composants (Header, Footer, Cards…)
* Mise en place des pages complètes : Présentation, Actions, Équipe, Contact
* Déploiement final sur le domaine : [assokaribu.com](https://assokaribu.com)
