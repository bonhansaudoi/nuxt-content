<template>
    <div class="container-card">
        <header class="space">
            <Back />

            <h1>topic adobe</h1> 
        </header>

        <div class="card">
            <div class="content">  
                <nav class="center-row">        
                    <NuxtLink 
                        v-for="tag of tags" 
                        :key="tag.slug"
                        :to="`/content/topic/adobe/${tag.slug}`"      
                        class="mb-4 py-1 px-2 lg:py-2 lg:px-4 mr-1 text-base lg:text-lg font-bold uppercase rounded-lg
                            text-white hover:bg-green-700 
                            transition-shadow duration-150 ease-in-out shadow-sm hover:shadow-md" 
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
    async asyncData({ $content }) {
        const tags = await $content('topic/adobe') 
        // const tags = await $content('adobe')
        .sortBy('number', 'asc')
        .fetch()
        return { tags }
    }  
} 
</script> 