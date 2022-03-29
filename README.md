# Meteor 2.7 Svelte Tailwindcss3 Routify

meteor create --svelte [project name]

meteor update —release 2.7

——————————————————————

## Tailwindcss 3.0

meteor npm install tailwindcss@latest postcss@latest postcss-load-config@latest autoprefixer@latest

Add to [/client/main.css]:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Create [postcss.config.js] and add:

```js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```

Create [tailwind.config.js] and add:

```js
module.exports = {
  content: [
    "./client/**/*.{html,js,svelte,ts}",
    "./imports/**/*.{html,js,svelte,ts}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

## Routify

meteor npm install --save @roxi/routify
meteor npm install npm-run-all

package.json:

```json
"scripts": {
"start": "run-p start:\*",
"start:meteor": "meteor run",
"start:routify": "routify",
"build": "routify -b",
"test": "meteor test --once --driver-package meteortesting:mocha",
"test-app": "TEST_WATCH=1 meteor test --full-app --driver-package meteortesting:mocha",
"visualize": "meteor --production --extra-packages bundle-visualizer"
},
```

App.svelte:
// Router Plugin - Routify

```js
import { Router } from "@roxi/routify";
import { routes } from "../routify/routes.js";
```
