# Vue + Inertia + Laravel + Bulma

Simple implementation of Vue + Inertia + Laravel + Bulma

## Steps - Vue + Inertia

01 - https://inertiajs.com/server-side-setup  

02 - https://inertiajs.com/client-side-setup  

04 - Call `vue` in `webpack.mix.js`  
```js
// and call vue()
mix.js('resources/js/app.js', 'public/js')
    .vue();
```  

05 - `npm install vue vue-loader --save-dev`  

06 - Create dir `Pages` in `./resources/js/`

07 - `npm i && npm run dev`  

## Steps - Bulma  

01 - `npm install -D tailwindcss@latest postcss@latest autoprefixer@latest`  

02 - `npx tailwindcss init`  

03 - Configure tailwind with `purge` in `tailwind.config.js`, add paths:  
```js
   purge: [
     './resources/**/*.blade.php',
     './resources/**/*.js',
     './resources/**/*.svelte',
   ]
```

04 - Configure Laravel Mix in `webpack.mix.js`  
```js
// add tailwindcss in postCss
mix.js("resources/js/app.js", "public/js")
    .postCss("resources/css/app.css", "public/css", [
        require("tailwindcss"),
    ]);
```

05 - Include directives in `./resources/css/app.css`  
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```