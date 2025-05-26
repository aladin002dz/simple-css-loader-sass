# Loader CSS en Code Sass

## Prérequis

Avant de commencer, assurez-vous d'avoir installé :

- Node.js (version LTS recommandée)
- npm (généralement installé avec Node.js)

**Vérifier l'installation de Node.js et npm**

```bash
node --version
npm --version
```

### Solution 1 (recommendée) : Créer un nouveau projet avec npm :

```bash
npm init -y
npm install -D sass
```

### Ajouter un script dans le fichier package.json :

```json
"scripts": {
  "dev": "sass --watch sass/main.scss:css/style.css",
  "build": "sass sass/main.scss:css/style.css --style=compressed"
}
```

## Structure du Projet

```
sass-starter/
├── css/          # Fichiers CSS compilés
├── sass/         # Fichiers source SASS
└── index.html    # Page principale
```

## Développement

Pour compiler les fichiers SASS en CSS, ouvrir le terminal et lancer la commande :

```bash
npm run dev
```

### arrêter le serveur se fait avec `ctrl + c`

Pour compiler les fichiers SASS en CSS compressé :

```bash
npm run build
```

### Pour initialiser Git

Créer un fichier `.gitignore` pour ignorer le dossier `node_modules`

```bash
git init
git add .
git commit -m "Initial commit"
```

## Solution 2 : Cloner le projet

forker le repo sur GitHub, ensuite cloner la version forkée en local

```bash
git clone git@github.com:aladin002dz/simple-css-loader-sass.git
   cd sass-starter
```

3. **Installer les dépendances**
   ```bash
   npm install
   ```

# Commencer le développement

```bash
npm run dev
```

# Les Fonctionnalités Clés de Sass

Sass (Syntactically Awesome Style Sheets) est un préprocesseur CSS qui offre de nombreuses fonctionnalités pour rendre le code CSS plus puissant et maintenable. Voici quelques exemples pratiques des fonctionnalités clés:

## 1. Variables

Les variables permettent de stocker des valeurs réutilisables comme des couleurs, tailles de police, ou espacements.

```scss
// Définition de variables
$primary-color: #3498db;
$secondary-color: #2ecc71;
$base-padding: 15px;
$font-stack: "Roboto", sans-serif;

.button {
  background-color: $primary-color;
  padding: $base-padding;
  font-family: $font-stack;
}

.alert {
  border: 1px solid $secondary-color;
  padding: $base-padding;
}
```

## 2. Imbrication (Nesting)

L'imbrication permet d'organiser le code CSS de manière hiérarchique, similaire à la structure HTML.

```scss
nav {
  background-color: #333;

  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li {
    display: inline-block;

    a {
      color: white;
      padding: 10px 15px;

      &:hover {
        text-decoration: underline;
      }
    }
  }
}
```

## 3. Importation de fichiers partiels

L'organisation modulaire du code avec des fichiers partiels.

```scss
@use "./reset";
@use "./composants/footer";
```

les fichiers partiels doivent commencer par un underscore "\_"

## 4. Media Queries imbriquées

Sass permet d'imbriquer les media queries directement dans les sélecteurs.

```scss
.navbar {
  display: flex;
  width: 100%;

  @media (min-width: 768px) {
    flex-direction: column;
  }

  .logo {
    margin-right: 20px;

    @media (min-width: 768px) {
      margin: 0 0 10px 0;
    }
  }
}
```

## 5. Nommer avec &

Permet de nommer un sélecteur avec un &

```scss
.button {
  &-primary {
    background-color: #2ecc71;
  }
  &-secondary {
    background-color: #3498db;
  }
  &:hover {
    background-color: #333;
  }
}
```
