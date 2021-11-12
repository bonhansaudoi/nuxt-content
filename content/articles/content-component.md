---
title: Components
date: 02-01-2021 
tags: content 
---  

<article>

### Accordation-Vue

```vue [pages/content/_slug.vue] 
<template>
    <div> 
        <div @click="readMore"
            class="accordation-btn cursor-pointer space-y-4"
        >
            <slot></slot>
        </div>

        <div class="accordation-content hidden" ref="content">
            <article>
                <slot name="content"></slot>
            </article>
        </div>
    </div> 
</template>

<script> 
export default {
    methods: {
        readMore () { 
            var c = document.getElementsByClassName("accordation-content");
            var i;

            function hideContent() {
                for (i = 0; i < c.length; i++) {
                    c[i].classList.add("hidden");
                } 
            }
          
           if (!this.$refs.content.classList.contains("hidden")) {
                this.$refs.content.classList.add("hidden");
            }
            else {
                hideContent();
                this.$refs.content.classList.toggle("hidden");
            } 
        }
    } 
}
</script>  
```

### accordation

``` [markdown]
<accordation> 

### title **<svg-right></svg-right>** 
<template v-slot:content> 

...

</template>
</accordation>
```
 
### readmore

``` [markdown]
### title  

<accordation>

........ <svg-readmore></svg-readmore>

<template v-slot:content>

........

</template> 
</accordation>

</article>