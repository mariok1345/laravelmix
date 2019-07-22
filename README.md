//instalacion de laravelmix

1.npm init -y
2.npm install laravel-mix --save-dev
3.cp -r node_modules/laravel-mix/setup/webpack.mix.js ./

4.integro el script en packaje.js

"scripts": {
    "dev": "npm run development",
    "development": "cross-env NODE_ENV=development node_modules/webpack/bin/webpack.js --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js",
    "watch": "npm run development -- --watch",
    "hot": "cross-env NODE_ENV=development node_modules/webpack-dev-server/bin/webpack-dev-server.js --inline --hot --config=node_modules/laravel-mix/setup/webpack.config.js",
    "prod": "npm run production",
    "production": "cross-env NODE_ENV=production node_modules/webpack/bin/webpack.js --no-progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js"
}

5. integro la ruta en el que se procesaran y compilaran nuestro archivos

const mix = require('laravel-mix');

 mix.js('resources/js/app.js', 'public/js')

 .sass('resources/sass/style.scss', 'public/css');


6.npm install cross-env --save-dev

7.npm run dev

8.npm rum watch

///////////////////////////////////////////////////////////////////////////////////////////////////////////
///instalcion de tailwindcss en laravelmix

1.npm i -D tailwindcss
2.npx tailwind init

3.tailwind.config.js plugins[

	require('tailwindcss'),
   require('autoprefixer'),
]


<!-- 4. @tailwind base;

   @tailwind components;

   @tailwind utilities;

   @import 'components/variables'
 -->

5 .luego si deseamos personalizar nuestros propios estilos solo  los importamos

//////////////////////////////////////////////////////////////////////////////////////////////////////////////
colocar .gitignore

node_modules/*
resources/*
webpack.mix.js
tailwind.config.js
package.json
mix-manifest.json
package-lock.json
