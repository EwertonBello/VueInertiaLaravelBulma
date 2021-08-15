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

01 - `npm install bulma`  

02 - Include directives in `./resources/css/app.css`  
```css
@import 'bulma/css/bulma.css'
```