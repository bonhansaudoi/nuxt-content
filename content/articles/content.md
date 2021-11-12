---
title: Nuxt-Content
description: Install-Config-Structure 
img: 
alt: 
author: 4Wao 
date: 01-01-2021 
tags: content 
---  

<article>

### Install-content-tailwindcss

```bash
npm init nuxt-app <project-name>
mkdir layouts plugins 
npm install vue-backtotop --save
```  

### Config
 
<accordation>

#### nuxt.config.js **<right></right>** 

<template v-slot:content>

```js [nuxt.config.js] 
export default {
    target: 'static',

	ssr: false,

	generate: {
		fallback: true
	}, 

    router: {
        base: '/content/'
    },

    content: {
		liveEdit: false,
	}, 

    loading: {
		color: 'blue'
	}, 

    plugins: [
		{ src: '~/plugins/vue-backtotop.js'},
	],

    build: {
		postcss: {
			plugins: {
				tailwindcss: {},
    			autoprefixer: {},
			}
		}  
	}
}
```
</template>
</accordation> 

<accordation>

#### prism **<right></right>** 

<template v-slot:content>

```js [plugins/prism.js]
import Prism from "prismjs";
import "prismjs/themes/prism-okaidia.css";
export default Prism;

Prism.languages.vue = Prism.languages.markup;
```

```js [_slug.vue]
import Prism from "~/plugins/prism.js"

mounted() {
    Prism.highlightAll();
},
``` 

```css []
.nuxt-content-highlight {
  @apply relative;
}
.nuxt-content-highlight .filename {
    @apply absolute right-6 z-10 mt-2 
    text-base text-green-600 font-semibold;
}
``` 
</template>
</accordation> 

### structure

<accordation>

#### folders **<right></right>** 

<template v-slot:content>

``` 
+ assets/
    + css/
    - tailwind.css

+ layouts/
    - default.vue
    - home.vue
    - error.vue

+ components/
    + global/
      
+ content/
    + articles/
    + tags/
        - window.md
        - linux.md
        - english.md
    + web/
        - vue.md
        - nuxt.md
        - content.md
        - django.md
        - laravel.md 
    + adobe/
        - photoshop.md
+ pages/ 
    + content/
        + category/
            _tags.vue 
        + web/
            _tags.vue 
        + adobe/
            _tags.vue 
        _slug.vue 
    + topics/
        - links.vue
        - web.vue
        - adobe.vue
    - index.vue 

+ plugins/ 
    - prism.js
    - vue-backtotop.js
    - toggle.js
``` 
</template> 
</accordation>

<accordation>

#### layouts **<right></right>** 

<template v-slot:content>  

```[default.vue]
<template>
    <main>   
		<Navbar />  
		 
        <Nuxt />

          <Top /> 
    </main>    	 
</template> 

<style lang="postcss">
html {@apply text-gray-600;}  
body {@apply bg-black;}  
h1 { @apply text-red-500; } 
h2 { @apply text-blue-500; }
h3 { @apply text-green-500; }    
h4 { @apply text-indigo-500 text-lg uppercase; } 

.nuxt-content {
    @apply break-words;
    & ul, & ol {
        @apply ml-4 md:ml-6 lg:ml-8 space-y-2;
        & ul, & ol {@apply ml-4 md:ml-6 lg:ml-8 space-y-2 mt-4;} 
    }  
} 
</style> 
```

```[error.vue]
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

```[home.vue]
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
</template> 
</accordation>

<accordation>

#### content **<right></right>**

<template v-slot:content>

```[articles/.md] 
---
title: vue  
description: 
img: 
alt: 
author:  
date: 01-01-2021   
tags: vue
---  
``` 

```[tags/.md ]
---
name: english
img: 
alt:  
date: 01-01-2021   
---
``` 

```[topics/.md ] 
---
name: vue
img: 
alt: 
date: 01-01-2021  
---
``` 
</template> 

</accordation> 

``` 
https://gilberttanner.com/blog/creating-a-blog-with-nuxt-content
``` 


## deploy

### Netlify 

+ client side rendering only in netlify: 
 
```js [nuxt.config.js] 

target: 'static',
ssr: false,
generate: {
   fallback: true
},
router: {
   base: '/content/'
},
```

```bash
npm run generate
```

#### create [Github-repository](https://pages.github.com/)

+ uncomment dist in .gitignore

``` [.gitignore]  

video/
test/ 
articles/content-test.md

```  

```bash

git init
git add . 
git remote add origin https://github.com/bonhansaudoi/nuxt-content.git
git commit -m "commit" 
git push -u origin master

```
  
#### create [Netlify-site](https://www.netlify.com/) 

+ Netlify GitHub app permissions
+ Create a new site
+ GitHub  
    + npm run generate  
    + dish
</article> 