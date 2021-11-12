<template>
    <nav class="navbar">  
        <div class="navbar-logo">
            <a  
                :href="logo.link" 
                class="logo inline-flex items-center"
            > 
                <svg class="fill-current" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M12.001 4.8c-3.2 0-5.2 1.6-6 4.8 1.2-1.6 2.6-2.2 4.2-1.8.913.228 1.565.89 2.288 1.624C13.666 10.618 15.027 12 18.001 12c3.2 0 5.2-1.6 6-4.8-1.2 1.6-2.6 2.2-4.2 1.8-.913-.228-1.565-.89-2.288-1.624C16.337 6.182 14.976 4.8 12.001 4.8zm-6 7.2c-3.2 0-5.2 1.6-6 4.8 1.2-1.6 2.6-2.2 4.2-1.8.913.228 1.565.89 2.288 1.624 1.177 1.194 2.538 2.576 5.512 2.576 3.2 0 5.2-1.6 6-4.8-1.2 1.6-2.6 2.2-4.2 1.8-.913-.228-1.565-.89-2.288-1.624C10.337 13.382 8.976 12 6.001 12z" />
                </svg>
                <span class="font-bold uppercase tracking-wide">
                    {{ logo.text }}
                </span>
            </a>

            <button class="hamberger lg:hidden">
                <svg class="block h-8 w-8 text-gray-500 font-bold" xmlns="http://www.w3.org/2000/svg"
                    fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hide="true">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M4 6h16M4 12h16M4 18h16" />
                </svg>
            </button>
        </div>

        <div class="navbar-menu hidden">  
            <div class="menu-link">  
                <Search /> 

                <div class="lg:space-x-6">  
                    <NuxtLink 
                        v-for="item in links"
                        :key="item.text"
                        :to="item.link" 
                    >
                        {{ item.text }}
                    </NuxtLink>  
                </div>  

                <div class="lg:inline-flex lg:space-x-6">       
                    <div class="dropdown relative"
                        v-for="item in dropdown" 
                        :key="item.text" 
                    >   
                        <button class="dropdown-btn 
                            inline-flex items-center text-left uppercase                
                            text-gray-400 
                            focus:text-green-500 hover:bg-gray-900 hover:text-white" 
                        >
                            {{ item.text }}

                            <svg class="h-4 w-4 ml-1 text-gray-500 font-bold" xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                            </svg>
                        </button>
            
                        <div class="dropdown-content 
                            hidden lg:absolute
                            lg:w-48 mt-1 lg:mt-4 p-2 text-sm  
                            border rounded-md shadow-md border-gray-500" 
                        >  
                            <NuxtLink 
                                v-for="item in item.content"
                                :key="item.text" 
                                :to="item.link" 
                                class="block"
                            >
                                {{ item.text }}
                            </NuxtLink>  
                        </div>  
                    </div>   
                </div>  
            </div> 
 
            <div class="navbar-right"> 
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
        </div> 
    </nav>
</template> 

<script>
import { hamberger, dropdown } from "~/plugins/toggle";  
export default {
    mounted () {
        hamberger();
        dropdown();
    },
    // data: () => ({ 
    data () {
        return {  
			logo: { 
               	text: '4WAO', 
				link: 'https://bonhansaudoi.github.io/sadMiss/src/'        
            }, 
            links: [ 
                {
                    text: "home",
                    link: "/"
                },
                {
                    text: "links",
                    link: "/links"
                },
			], 
            dropdown: [               
                { 
                    text: "category",
                    content: [
                        {       
                            text: 'web',
                            link: '/content/topic/web'   
                        },
                        {       
                            text: 'adobe',
                            link: '/content/topic/adobe'   
                        },
                        {       
                            text: 'window',
                            link: '/content/category/window'   
                        },
                        {       
                            text: 'linux',
                            link: '/content/category/linux'   
                        },
                        {       
                            text: 'english',
                            link: '/content/category/english'   
                        } 
                    ] 				   
                } 
            ] 
		}
	}  
}
</script> 

<style lang="postcss"> 
.navbar {@apply text-gray-400;} 
.logo {@apply lg:mr-6;} 
.logo svg {@apply h-8 w-8 mr-2 text-orange-400;} 
.logo span {@apply text-xl mr-2 text-orange-400;}
.hamberger svg {@apply hover:text-green-500 focus:text-green-500;}
.search {@apply lg:right-52;} 
.menu-link a, .menu-link .dropdown, .menu-link .signin, .menu-link .signup {
    @apply hover:text-white hover:bg-gray-900;
}
.dropdown-btn {@apply focus:text-green-500 hover:bg-gray-900 hover:text-white;}
.dropdown-content {@apply bg-white;}  
.navbar-right {@apply flex items-center space-x-6 lg:space-x-8;} 
</style>  