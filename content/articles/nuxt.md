---
title: nuxt
description: Install-Config-Structure 
img: 
alt: 
author: 4Wao 
date: 01-01-2021 
tags: nuxt
---  

<article>  

### Install Nuxt-Tailwindcss

```bash
npm init nuxt-app <project-name>
mkdir layouts plugins middleware modules  
npm install vue-backtotop --save 
```

### Config

```js [nuxt.config.js]

loading: {
    color: 'blue'
},

{ hid: 'description', name: 'description', content: '' },
 
plugins: [
    { src: '~plugins/vue-backtotop.js', ssr: false }  
],
 
build: {
    postcss: {
        plugins: {
            tailwindcss: {},
            autoprefixer: {},
        }
    },  
    // babel:{
    //     plugins: [
    //         ['@babel/plugin-proposal-private-methods', { loose: true }]
    //     ]
    // }
}
```

```css [assets/css/tailwind.css]
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {} 
@layer components {} 
@layer utilities {}   
```

```css [assets/css/app.css] 

ul li > * > *, ol li > * > * {list-style-type: circle;}  

/* layout-transition */ 
.layout-enter-active, .layout-leave-active {
   transition: opacity 0.5s;
}
.layout-enter, .layout-leave-active {
   opacity: 0;
} 

/* page-transition */
.page-enter-active, .page-leave-active { 
   transition: opacity 0.5s;
}
.page-enter, .page-leave-active { 
   opacity: 0;
} 
``` 

```js [plugins/vue-backtotop.js]

import Vue from 'vue'
import BackToTop from 'vue-backtotop'

Vue.use(BackToTop)
```

### structure

#### folders 

```
+ assets/
    + css/
        - tailwind.css

+ layouts/
    - default.vue
    - home.vue
    - error.vue

+ pages/ 

+ plugins/  
    - vue-backtotop.js
    - toggle.js  
```

#### layouts

```vue [default.vue]
<template>
    <main>   
		<Navbar />  
		 
        <Nuxt />

          <Top /> 
    </main>    	 
</template> 

<style lang="postcss"></style> 
```

```vue [error.vue]
<template>
    <div class="">
        <h1 v-if="error.statusCode === 404">Page not found</h1>
        <h2 v-else>An error occurred</h2>
        <NuxtLink to="/">Home page</NuxtLink>
    </div>
</template>

<script>
export default {
    props: ['error'],
    layout: 'error'  
}
</script>
```

```vue [home.vue]
<template>
    <div> 
        <div class="absolute top-0 right-0 bottom-0 lg:inset-0 -z-3">
            <img src="https://s4.gifyu.com/images/waterfall.png" alt="waterfall" class="object-cover w-full h-full">
        </div>
    
        <div class="hidden lg:block absolute inset-0 -z-2 lg:overflow-hidden bg-transparent">
            <video class="-mt-20" autoplay muted loop>
                <source src="~/assets/video/water-fall.mp4" type="video/mp4">
            </video>

            <div class="absolute inset-0 bg-black opacity-30"></div>
        </div> 
        
        <main class="main"> 
            <Nuxt />        
        </main>
    </div>
</template> 
```

```vue [pages/index.vue]

<template> 
    <div></div> 
</template>

<script>
export default {
    layout: 'home', 
    data () {
        return {} 
    }, 
}
</script> 

<style>
ul li > * > *, ol li > * > * {list-style-type: circle;}  
</style> 
``` 