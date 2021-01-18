# Starter project for Tailwind CSS

## Init project

```npm init -y ```

## Install requirement

```npm install tailwindcss postcss-cli autoprefixer cssnano```

## Init Tailwind CSS

``` npx tailwindcss init ```

## Create postcss.config.js

Add this content :

```
module.exports = {
    plugins: [
        require('tailwindcss'),
        require('autoprefixer'),
    ]
}
```

## Update Tailwind.config.js
```
enabled: true,
    content: [
      './src/**/*.html',
      './src/**/*.vue',
      './src/**/*.jsx',
    ],
```

## Create folder dist

dist folder will contains generate index.css

## Create index.css & index.html

Add this to index.css
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
And add basic skeleton on index.html and import dist/index.css

## Update package.json

Add this scripts:

```
  "scripts": {
    "tailwind": "npx tailwindcss build index.css -o dist/index.css",
    "autoprefixer": "postcss dist/index.css -u autoprefixer --no-map -o dist/index.css",
    "minify": "postcss dist/index.css -u cssnano --no-map -o dist/index.min.css",
    "build": "npm run tailwind && npm run autoprefixer",
    "production": "npm run tailwind && npm run autoprefixer && npm run minify"
  },
```

## Sources 

- https://les-enovateurs.com/tailwind-css-partie-1-apprehender-ce-framework-css-rapidement/

- https://dev.to/tomaszbujnowicz/setup-tailwind-css-in-20-seconds-without-nodemodules-1b83
    
- https://medium.com/codingthesmartway-com-blog/tailwind-css-for-absolute-beginners-3e1b5e8fe1a1
