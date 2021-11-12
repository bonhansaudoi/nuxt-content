<template> 
    <div class="container-card">
        <Back />

        <div class="card"> 
            <div class="content"> 
                <h1>{{ article.title }}</h1>

                <div class="space-y-4">     
                    <InfoArticle :article="article" />  

                    <ContentTable :article="article" /> 
                </div> 

                <nuxt-content :document="article" />    
      
                <PrevNext :prev="prev" :next="next" />  
             </div>     
        </div>  
    </div>
</template>

<script>
import Prism from "~/plugins/prism";

export default { 
    mounted() {
        Prism.highlightAll();
    },
    
    async asyncData({ $content, params }) { 
        // const article = await $content('articles', { deep: true }).fetch() 
        const article = await $content('articles', params.slug , { deep: true }).fetch() 
 
        const [prev, next] = await $content('articles')
            .sortBy('createdAt', 'asc')
            .surround(params.slug)
            .fetch()

        return {
            article,
            prev,
            next
        }   
    } 
}
</script>  


<style lang="postcss" scoped>
</style>
 
