<template> 
    <div>  
        <nav class="flex justify-between px-4 md:px-6 text-base md:text-2xl mt-4"> 
            <div class="flex justify-between">
                <a href="https://bonhansaudoi.github.io/sadMiss/src/mySad.html"
                    class="inline-flex items-center text-white">
                    <svg class="fill-current h-8 w-8 mr-2" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M12.001 4.8c-3.2 0-5.2 1.6-6 4.8 1.2-1.6 2.6-2.2 4.2-1.8.913.228 1.565.89 2.288 1.624C13.666 10.618 15.027 12 18.001 12c3.2 0 5.2-1.6 6-4.8-1.2 1.6-2.6 2.2-4.2 1.8-.913-.228-1.565-.89-2.288-1.624C16.337 6.182 14.976 4.8 12.001 4.8zm-6 7.2c-3.2 0-5.2 1.6-6 4.8 1.2-1.6 2.6-2.2 4.2-1.8.913.228 1.565.89 2.288 1.624 1.177 1.194 2.538 2.576 5.512 2.576 3.2 0 5.2-1.6 6-4.8-1.2 1.6-2.6 2.2-4.2 1.8-.913-.228-1.565-.89-2.288-1.624C10.337 13.382 8.976 12 6.001 12z" />
                    </svg>

                    <span class="text-xl font-bold uppercase tracking-wide mr-4">
                        BoNhanSauDoi
                    </span>
                </a>
            </div>

            <div class="flex justify-between space-x-4 lg:space-x-8 lg:ml-auto">
                <a href="https://trangnhat.net/" target="_blank">
                    <svg class="w-8 h-8 text-green-500" fill="currentColor" viewBox="0 0 20 20"
                        xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd"
                            d="M4.083 9h1.946c.089-1.546.383-2.97.837-4.118A6.004 6.004 0 004.083 9zM10 2a8 8 0 100 16 8 8 0 000-16zm0 2c-.076 0-.232.032-.465.262-.238.234-.497.623-.737 1.182-.389.907-.673 2.142-.766 3.556h3.936c-.093-1.414-.377-2.649-.766-3.556-.24-.56-.5-.948-.737-1.182C10.232 4.032 10.076 4 10 4zm3.971 5c-.089-1.546-.383-2.97-.837-4.118A6.004 6.004 0 0115.917 9h-1.946zm-2.003 2H8.032c.093 1.414.377 2.649.766 3.556.24.56.5.948.737 1.182.233.23.389.262.465.262.076 0 .232-.032.465-.262.238-.234.498-.623.737-1.182.389-.907.673-2.142.766-3.556zm1.166 4.118c.454-1.147.748-2.572.837-4.118h1.946a6.004 6.004 0 01-2.783 4.118zm-6.268 0C6.412 13.97 6.118 12.546 6.03 11H4.083a6.004 6.004 0 002.783 4.118z"
                            clip-rule="evenodd"></path>
                    </svg>
                </a>
                <a href="https://www.youtube.com/" target="_blank">
                    <img src="~/assets/img/youtube.svg" width="30" height="30" alt="youtube">
                </a>
                <a href="https://www.facebook.com/" target="_blank">
                    <img src="~/assets/img/facebook.svg" width="30" height="30" alt="facebook">
                </a>
            </div>
        </nav>

        <div class="center">
            <img class="w-52 h-52 lg:w-72 lg:h-72 my-10 lg:my-10" src="https://s5.gifyu.com/images/tiger-logo.png">

            <div class="center greeting space-y-4 lg:space-y-6">
                <div class="text-2xl lg:text-5xl font-bold uppercase text-orange-500">
                    NOT Welcome to 4Wao Blog
                </div>

                <button class="py-2 px-4">
                    <a href="https://bonhansaudoi.github.io/sadMiss/src/"
                        class="text-2xl lg:text-3xl font-extrabold text-purple-700 hover:text-white hover:bg-green-700 rounded-xl">
                        ❤️ MY MISS ❤️
                    </a>
                </button> 

                <nav class="center-row">
                    <NuxtLink 
                        v-for="item in topic" :to="item.to"
                        :key="item.text" 
                        class="text-lg lg:text-xl font-bold uppercase 
                            text-white hover:bg-green-700 
                            mb-4 py-1 px-2 lg:py-2 lg:px-4 mr-1 rounded-lg" 
                    >  
                        {{ item.text }}  
                    </NuxtLink>  
                </nav>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    layout: 'home', 
    data () {
        return { 
            topic: [
                {
                    text: 'links',  
                    to: '/links',
                },
                {
                    text: 'web', 
                    to: '/content/topic/web/',
                },
                {
                    text: 'adobe', 
                    to: '/content/topic/adobe/',
                },
                {
                    text: 'window', 
                    to: '/content/category/window/',
                },
                {
                    text: 'linux', 
                    to: '/content/category/linux/',
                }, 
                {
                    text: 'english', 
                    to: '/content/category/english/',
                }, 
            ] 
        } 
    }, 
}
</script> 

<style> 
    .center img {
        animation: fadeIn 1s linear;
    }

    @keyframes fadeIn {
        0% {
            opacity: 0;
            transform: scale(0);
        } 
        100% {
            opacity: 1;
            transform: scale(1);
        }
    }

    .greeting {
        animation: rotate 2s linear;
    } 
    @keyframes rotate {
        0% {
            opacity: 0;
            transform: rotateY(180deg);
        } 
        50% {
            opacity: 0.3;
            transform: rotateY(180deg);
        } 
        100% {
            opacity: 1;
        }
    }
</style>