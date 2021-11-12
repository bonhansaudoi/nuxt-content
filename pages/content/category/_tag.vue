<template>
    <div class="container-card">
        <header class="space">
            <Back />
            
            <div v-for="tag of tags" :key="tag.slug">               
                <h1>posts of {{ tag.name }} </h1> 
            </div>
        </header>

        <div class="card">
            <div class="content">  
                <div v-for="article of articles" :key="article.slug">   
                    <NuxtLink 
                        :to="{ name: 'content-slug', params: { slug: article.slug }}"
                    >
                        <div class="card">
                            <div class="content">
                                <h3>{{ article.title }}</h3> 
    
                                <div class="description text-base lg:text-lg text-white">
                                    {{ article.description }}  
                                
                                    <div class="mt-2"> 
                                        <Readmore />
                                    </div> 
                                </div> 
                            </div>
                        </div>
                    </NuxtLink>   
                </div>           
            </div>
        </div> 
    </div>
</template>

<script> 
export default { 
    async asyncData({ $content, params }) {
        const tags = await $content('tags')
            .where({ slug: { $contains: params.tag } })
            .fetch()

        const tag = tags.length > 0 ? tags[0] : {}
        //  const articles = await $content('articles')
       const articles = await $content('articles', { deep: true })
            .where({ tags: { $contains: tag.name } })
            .sortBy('date', 'asc')
            .fetch()

        return {
            tags, articles
        }
    }  
} 
</script> 

<style lang="postcss" scoped> 
</style>