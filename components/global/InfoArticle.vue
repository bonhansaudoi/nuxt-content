<template>
    <div class="flex justify-between 
        uppercase font-bold
        mb-8"
    >
        <div class="flex flex-col space-y-4 ">
            <span>Author: {{ article.author }}</span>
            <span>Updated at: {{ formatDate(article.updatedAt) }}</span>
        </div>

        <div class="flex space-x-2 lg:space-x-4">
            <span>Social</span>
            <span>Comments: 0</span>
            <span>Discribe</span>
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
    methods: {
        formatDate(date) {
            const options = { year: 'numeric', month: 'numeric', day: 'numeric' }
            return new Date(date).toLocaleDateString('vni', options)
        },
    }
}
</script> 