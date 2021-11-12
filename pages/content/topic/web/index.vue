<template>
    <div class="container-card">	
        <Back /> 

        <div class="card">  
            <div class="content"> 
                <h1>topic web</h1>  
                <nav class="center-row">                 
                    <NuxtLink 
                        v-for="tag of tags" 
                        :key="tag.slug"
                        :to="`/content/topic/web/${tag.slug}`"      
                        class="py-1 px-3 lg:mr-4 
                            lg:text-lg font-bold uppercase rounded-lg
                            text-white hover:bg-green-700" 
                        >
                        {{ tag.name }} 
                    </NuxtLink>  
                </nav>                  
            </div>
        </div> 
    </div>
</template>

<script> 
export default {  
    async asyncData({$content }) {
        const tags = await $content('topic/web')
        // const tags = await $content('web')
        .sortBy('number', 'asc')
        .fetch()
        // return { tags }

        //const article = await $content('articles', { deep: true }, params.slug).fetch() 
       
const article = await $content('articles/web').fetch()

        return {
            tags,
            article
        } 
    }  
} 
</script> 


<style lang="postcss" scoped> 
</style>