 <template>
    <div id="">
        <div class="container-card">
            <Back /> 
            
            <div class="card"> 
                <div class="content">
                    <h1>{{ title }}</h1> 

                    <nav class="center-row mt-4 md:mt-6 lg:mt-8"> 
                        <NuxtLink v-for="item in loop" :key="item.text"                   
                            :to="item.to"      
                            class="px-2 mb-4 rounded-lg
                                lg:text-lg font-bold uppercase
                                text-gray-500 hover:text-white hover:bg-green-700" 
                        >
                            {{ item.text }} 
                        </NuxtLink>    
                    </nav>   
                    
                    <div v-for="item in loop" :key="item.text" 
                        class="space"
                    >  
                        <h3 :id=" item.id" class="uppercase"> 
                            {{ item.text }}
                        </h3>

                        <nav class="inline-flex space-x-2"
                            v-for="item in item.contents"
                            :key="item.text"  
                        > 
                            <a target="_blank"
                                :href="item.link"
                                class="py-1 px-3 mr-4 
                                border-2 rounded-lg border-gray-500 
                                hover:bg-green-700
                                lg:text-lg text-white uppercase"
                            >
                                {{ item.text }}
                            </a>   
                        </nav>
                    </div>  
                </div>           
            </div>
        </div> 
    </div>   
</template>

<script> 
export default { 
	data () {
        return {     
            title: 'web link',
             
            loop: [
// news
                {
                    text: 'news', id: 'news', to: '/links/#news', 
                    contents: [
                        {
                            text: 'thanhnien',
                            link: 'https://thanhnien.vn/' 
                        },
                        {
                            text: 'tuoitre',
                            link: 'https://tuoitre.vn/' 
                        },
                        {
                            text: 'msn',
                            link: 'https://www.msn.com/vi-vn/' 
                        },
                        {
                            text: 'baomoi',
                            link: 'https://baomoi.com/' 
                        },
                        {
                            text: 'bbc',
                            link: 'https://www.bbc.com/' 
                        },
                        {
                            text: 'voanews',
                            link: 'https://www.voanews.com/' 
                        },
                        {
                            text: 'news-au',
                            link: 'https://www.news.com.au/' 
                        },
                        {
                            text: 'abc-au',
                            link: 'https://www.abc.net.au/radio-australia/' 
                        },
                        {
                            text: 'msn-au',
                            link: 'https://www.msn.com/en-au/news/australia' 
                        },
                    ]
                },               
// document
                {
                    text: 'document', id: 'document', to: '/links/#document', 
                    contents: [ 
                        {
                            text: 'W3School',
                            link: 'https://www.w3schools.com/'              
                        },
                        {
                            text: 'scotch',
                            link: 'https://scotch.io/',       
                        },
                        {
                            text: 'Mozilla',
                            link: 'https://developer.mozilla.org/en-US/',       
                        },
                        {
                            text: 'w3org',
                            link: 'https://www.w3.org/Style/CSS/Overview.en.html',       
                        },
                        {
                            text: 'python',
                            link: 'https://www.python.org/',       
                        },
                        {
                            text: 'php',
                            link: 'https://www.php.net/manual/en/langref.php',       
                        },
                        {
                            text: 'json',
                            link: 'https://www.json.org/json-en.html',       
                        }, 
                        {
                            text: 'javascript',
                            link: 'https://www.javascript.com/',       
                        },
                        {
                            text: 'es6',
                            link: 'http://es6-features.org/',       
                        },
                    ], 
                    style:  {  
                        color: 'red',
                        background: 'blue'  
                    }                           
                },
// framework
                {
                    text: 'framework', id: 'framework', to: '/links/#framework', 
                    contents: [ 
                        {
                            text: 'vue',
                            link: 'https://vuejs.org/',       
                        },
                        {
                            text: 'router',
                            link: 'https://router.vuejs.org/',       
                        },
                        {
                            text: 'vuex',
                            link: 'https://vuex.vuejs.org/',       
                        },
                        {
                            text: 'nuxt',
                            link: 'https://nuxtjs.org/',       
                        },
                        {
                            text: 'content',
                            link: 'https://content.nuxtjs.org/',       
                        },
                        {
                            text: 'vuepress',
                            link: 'https://vuepress.vuejs.org/'    
                        },
                        {
                            text: 'django',
                            link: 'https://www.djangoproject.com/',       
                        },
                        {
                            text: 'laravel',
                            link: 'https://laravel.com/',       
                        },
                         {
                            text: 'tailwindcss',
                            link: 'https://tailwindcss.com/',       
                        },             
                        {
                            text: 'boostrap',
                            link: 'https://www.javascript.com/',       
                        },          
                        {
                            text: 'vuetify',
                            link: 'https://vuetifyjs.com/en/',       
                        },
                        {
                            text: 'stylus',
                            link: 'https://stylus-lang.com/',       
                        },          
                        {
                            text: 'sass',
                            link: 'https://sass-lang.com/guide',       
                        },                
                        {
                            text: 'jquery',
                            link: 'https://code.jquery.com/',       
                        },  
                        {
                            text: 'babeljs',
                            link: 'https://babeljs.io/docs/en/learn',       
                        },
                        {
                            text: 'typescript',
                            link: 'https://www.typescriptlang.org/',       
                        },
                        {
                            text: 'webpack',
                            link: 'https://webpack.js.org/',       
                        },
                        {
                            text: 'nodejs',
                            link: 'https://nodejs.org/en/',       
                        },
                        {
                            text: 'composer',
                            link: 'https://getcomposer.org/',       
                        },                      
                        {
                            text: 'git',
                            link: 'https://guides.github.com/introduction/git-handbook/',       
                        },
                        {
                            text: 'Markdown',
                            link: 'https://www.markdownguide.org/basic-syntax/',       
                        }, 
                        {
                            text: 'Frontmatter',
                            link: 'https://jekyllrb.com/docs/front-matter/',       
                        },                 
                    ]
                },
// font
                {
                    text: 'font', id: 'font', to: '/links/#font', 
                    contents: [ 
                        {
                            text: 'heroicons',
                            link: 'https://heroicons.dev/',       
                        },
                        {
                            text: 'icons',
                            link: 'https://icon-icons.com/',       
                        }, 
                        {
                            text: 'flaticon',
                            link: 'https://www.flaticon.com/',       
                        }, 
                        {
                            text: 'emojipedia',
                            link: 'https://emojipedia.org/',       
                        }, 
                    ]
                },  
// Editor  
                {
                    text: 'Editor', id: 'Editor', to: '/links/#Editor', 
                    contents: [ 
                        {
                            text: 'visualstudio',
                            link: 'https://code.visualstudio.com/',       
                        },
                        {
                            text: 'snippet-generator',
                            link: 'https://snippet-generator.app/',       
                        }, 
                        {
                            text: 'sublimetext',
                            link: 'https://www.sublimetext.com/',       
                        }, 
                        {
                            text: 'packagecontrol',
                            link: 'https://packagecontrol.io/',       
                        },
                        {
                            text: 'emmet',
                            link: 'https://docs.emmet.io/',       
                        },
                        {
                            text: 'ckeditor',
                            link: 'https://ckeditor.com/',       
                        },
                        {
                            text: 'summernote',
                            link: 'https://summernote.org/',       
                        },
                    ]
                },                      
// host
                {
                    text: 'host', id: 'host', to: '/links/#host', 
                    contents: [ 
                        {
                            text: 'Github',
                            link: 'https://github.com/',       
                        },
                        {
                            text: 'gifyu',
                            link: 'https://gifyu.com/?lang=vi',       
                        },
                        {
                            text: 'photobucket',
                            link: 'https://s1122.photobucket.com/user/vannhanhello/library/?sort=3&page=0',       
                        },
                        {
                            text: 'flickr',
                            link: 'https://www.flickr.com/',       
                        },
                        {
                            text: 'drive',
                            link: 'https://drive.google.com/drive/my-drive',       
                        },
                        {
                            text: 'google',
                            link: 'https://myaccount.google.com/',       
                        },
                        {
                            text: 'nestlify',
                            link: 'https://www.netlify.com/" class="btn btn-outline-success mr-2',       
                        },
                        {
                            text: 'firebase',
                            link: 'https://firebase.google.com/docs/" class="btn btn-outline-success mr-2',       
                        },
                        {
                            text: 'heroku',
                            link: 'https://id.heroku.com/',       
                        },
                        {
                            text: 'hostinger',
                            link: 'https://www.hostinger.vn/free-hosting',       
                        },
                        {
                            text: '000webhost',
                            link: 'https://vn.000webhost.com/',       
                        },
                        {
                            text: 'youtube',
                            link: 'https://www.youtube.com/feed/library',       
                        },
                        {
                            text: 'zingmp3',
                            link: 'https://zingmp3.vn/',       
                        },
                        {
                            text: 'nct',
                            link: 'http://www.nhaccuatui.com/',       
                        },
                        {
                            text: 'zalo',
                            link: 'https://zalo.me/pc#',       
                        },
                    ],
                }, 
// developer
                {
                    text: 'developer', id: 'developer', to: '/links/#developer',
                    contents: [ 
                        {
                            text: 'facebook',
                            link: 'https://developers.facebook.com/',       
                        },
                        {
                            text: 'google',
                            link: 'https://console.developers.google.com/',       
                        },
                        {
                            text: 'recaptcha',
                            link: 'https://www.google.com/recaptcha/intro/v3.html',       
                        },
                    ] 
                }, 
// Server                
                {
                    text: 'Server', id: 'Server', to: '/links/#Server',
                    contents: [
                        {
                            text: 'MYSQL',
                            link: 'https://www.mysql.com/downloads/' 
                        },
                        {
                            text: 'Laragon',
                            link: 'https://laragon.org/"' 
                        },
                        {
                            text: 'wampserver',
                            link: 'http://www.wampserver.com/en/' 
                        },
                         {
                            text: 'Xamp',
                            link: 'https://www.apachefriends.org/download.html' 
                        },
                        {
                            text: 'Filezille',
                            link: 'https://filezilla-project.org/download.php' 
                        }, 
                    ]
                }, 
// English s
                {
                    text: 'English', id: 'English', to: '/links/#English',
                    contents: [
                        {
                            // text: '',
                            // link: '' 
                        } 
                    ]
                }, 
// library
                {
                    text: 'library', id: 'library', to: '/links/#library',
                    contents: [ 
                        {
                            text: 'animate.css',
                            link: 'https://animate.style/',       
                        },   
                        {
                            text: 'velocityjs',
                            link: 'http://velocityjs.org/',       
                        }, 
                        {
                            text: 'animejs',
                            link: 'https://animejs.com/',       
                        }, 
                        {
                            text: '',
                            link: '',       
                        },   
                        {
                            text: 'cubic-bezier',
                            link: 'https://cubic-bezier.com/#.17,.67,.83,.67',       
                        },   
                        {
                            text: 'date-moment',
                            link: 'http://zetcode.com/javascript/momentjs/',       
                        },   
                    ]
                }, 
// online
                {
                    text: 'online', id: 'online', to: '/links/#online',
                    contents: [ 
                        {
                            text: 'loremipsum',
                            link: 'https://loremipsum.io/21-of-the-best-placeholder-image-generators/',       
                        }, 
                        {
                            text: 'placeholder-lorem',
                            link: 'https://placeholder.com/text/lorem-ipsum/',       
                        }, 
                        {
                            text: 'prismic',
                            link: 'https://prismic.io/',       
                        }, 
                        {
                            text: 'jsonplaceholder',
                            link: 'https://jsonplaceholder.typicode.com/',       
                        }, 
                        {
                            text: 'placeholder',
                            link: 'https://placeholder.com/',       
                        }, 
                         {
                            text: 'codebeautify',
                            link: 'https://codebeautify.org/html-escape-unescape',       
                        }, 
                        {
                            text: 'minifycode',
                            link: 'http://minifycode.com/css-minifier/',       
                        }, 
                        {
                            text: 'unminify',
                            link: 'https://unminify.com/',       
                        }, 
                        {
                            text: 'beautifytools',
                            link: 'http://beautifytools.com/scss-compiler.php',       
                        }, 
                        {
                            text: 'imagecolorpicker',
                            link: 'https://imagecolorpicker.com/',       
                        }, 
                    ]
                },                        
//Referrence               
                {
                    text: 'referrence', id: 'referrence', to: '/links/#referrence',
                    contents: [
                        {
                            text: 'hostingviet',
                            link: 'https://hostingviet.vn/pwa-la-gi' 
                        } 
                    ]
                }, 
            ] 
        }
    } 
}
</script>  