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

05 - `npm install vue vue-loader @vue/compiler-sfc --save-dev`  

06 - Create dir `Pages` in `./resources/js/`

07 - `npm i && npm run dev`  

## Steps - Bulma  

01 - `npm install bulma --save-dev`  

02 - Include directives in `./resources/css/app.css`  
```css
@import 'bulma/css/bulma.css'
```

## Steps - Typescript

01 - `npm install ts-loader typescript --save-dev`  

02 - `npx tsc --init` and add recommended configuration in `tsconfig.json`  
reference: https://v3.vuejs.org/guide/typescript-support.html#recommended-configuration  
```json
// tsconfig.json
{
  "compilerOptions": {
    "target": "esnext",
    "module": "esnext",
    // this enables stricter inference for data properties on `this`
    "strict": true,
    "jsx": "preserve",
    "moduleResolution": "node"
  }
}
```

03 - Replace file `/resources/js/app.js` to `/resources/js/app.ts`  

04 - Replace `App` to `app`  
```ts
setup({ el, app, props, plugin }) {
  createApp({ render: () => h(app, props) })
```

05 - Replace `.js` to `.ts`  
```ts
// ./webpack.mix.js

//add mix.ts and app.ts
mix.ts('resources/js/app.ts', 'public/js')
```

06 - Create `webpack.config.js`  
```js
const path = require("path");

module.exports = {
    output: {
      chunkFilename: 'js/[name].js?id=[chunkhash]',
    },
    resolve: {
      alias: {
        '@': path.resolve('./resources/js'),
        '~': path.resolve('./'),
      },
    },
}

// And import in webpack.mix.js
const config = require('./webpack.config');
//add to webpackConfig in mix.ts()
.webpackConfig(config);

```
