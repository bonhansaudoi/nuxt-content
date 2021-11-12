<template> 
    <div class="search lg:absolute lg:top-2">
        <div class="relative">
            <svg class="h-5 absolute mt-3 ml-3" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
            </svg>
            <input type="search" placeholder="Search" class="w-64 lg:w-72 py-2 pl-10 
                text-gray-500 font-semibold 
                border border-gray-500 rounded-pill
                bg-gray-200"
            >  
        </div> 
    </div>  
</template>

<script>
export default {
    data() {
        return {
            searchQuery: '',
            articles: []
        }
    },
    watch: {
        async searchQuery(searchQuery) {
            if (!searchQuery) {
                this.articles = []
                return
            }
            
            this.articles = await this.$content('articles')
                .limit(6)
                .search(searchQuery)
                .fetch()
        }  
    }
}
</script>