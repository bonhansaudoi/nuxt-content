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

article { @apply lg:text-lg;}
 
.nuxt-content {
    @apply break-words;  
    & ul, & ol {
        @apply ml-4 md:ml-6 lg:ml-8 space-y-2;
        & ul, & ol {@apply ml-4 md:ml-6 lg:ml-8 space-y-2 mt-4;} 
    } 
     
} 
</style>  