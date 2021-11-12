<template>
    <div> 
        <div @click="accordation"
            class="accordation-btn cursor-pointer space-y-4"
        >
            <slot></slot>
        </div>

        <div class="accordation-content hidden" ref="content">
            <article>
                <slot name="content"></slot>
            </article>
        </div>
    </div> 
</template>

<script> 
export default {
    methods: {
        accordation () { 
            var c = document.getElementsByClassName("accordation-content");
            var i;

            function hideContent() {
                for (i = 0; i < c.length; i++) {
                    c[i].classList.add("hidden");
                } 
            }
          
           if (!this.$refs.content.classList.contains("hidden")) {
                this.$refs.content.classList.add("hidden");
            }
            else {
                hideContent();
                this.$refs.content.classList.toggle("hidden");
            }

            // window.onclick = function(event) {
            //     if (!event.target.matches('.accordation-btn')) {
            //         var c = document.getElementsByClassName("accordation-content");
            //         var i;
            //         for (i = 0; i < c.length; i++) {
            //             var closeContent = c[i];
            //             if (!closeContent.classList.contains('hidden')) {
            //                 closeContent.classList.add('hidden');
            //             }
            //         }
            //     }
            // }
        }
    } 
}
</script>  