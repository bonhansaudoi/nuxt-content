<template>            
   <div class="">
      <h3>Content Table:</h3>

      <div class="ml-8 mt-4"
         v-for="link of article.toc"
         :key="link.id"
         :class="{ 'toc2': link.depth === 2, 'toc3': link.depth === 3 }"
      >
         <NuxtLink :to="`#${link.id}`" class="uppercase"> 
            {{ link.text }}
         </NuxtLink>
      </div>
   </div>
</template>

<script>
export default {
   props: {
      article: {
         type: Object,
         required: true
      }
   },
}
</script>

<style lang="postcss" scoped>
.toc3 {
   @apply ml-8;
}
</style>
 