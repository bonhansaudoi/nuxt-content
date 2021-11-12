---
title: nuxt-snippet
description:   
img: 
alt: 
author:  
date: 03-01-2021 
tags: nuxt
---

### Loop links

```vue
<NuxtLink 
    v-for="item in menuLinks"
    :key="item.text"
    :to="item.to"        
    class=""
>
    {{ item.text }}
</NuxtLink>  

data () {
    return {
        menuLinks: [ 
            {
                text: "home",
                to: "/"
            },
            {
                text: "links",
                to: "/content/topic/links/#links"
            },
        ], 
    }
}
```