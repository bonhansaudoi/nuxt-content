<template>
    <div class="dropdown-full hidden lg:block">
        <button class="dropdown-btn
            inline-flex items-center text-left uppercase
            text-gray-400 
            focus:text-green-500 hover:bg-gray-900 hover:text-white">
            test
            <svg class="h-4 w-4 ml-1 text-gray-500 font-bold" xmlns="http://www.w3.org/2000/svg" fill="none"
                viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
            </svg>
        </button>

        <div class="dropdown-content 
            hidden lg:absolute lg:left-6 lg:right-6 
            mt-1 lg:mt-4 p-2 text-sm  
            border rounded-md shadow-md border-gray-500"  
        >    
            <div class="lg:flex justify-between">  
                <a href="http://127.0.0.1:5500/public/test/layout.html" class="text-red-500 hover:bg-gray-100">
                    Layout
                </a>
                <a href="http://127.0.0.1:5500/public/test/bar/navbar.html" class="text-red-500 hover:bg-gray-100">
                    Navbar
                </a>
                <a href="http://127.0.0.1:5500/public/test/effect/effect.html" class="text-red-500 hover:bg-gray-100">
                Effect
                </a> 
            </div>
        </div>
    </div>
</template> 