<template> 
	<button type="button" @click="back"
		class="lg:text-lg uppercase font-bold 
			text-gray-500 hover:text-gray-700"
		>
		<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"
			class="inline-flex items-center h-5 w-5 -mt-1 text-gray-500">
			<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 19l-7-7 7-7m8 14l-7-7 7-7" />
		</svg>
		
		Back
	</button>
</template>

<script>
export default {
	methods: {
		back () {
			//this.$router.go(-1);
			this.$router.back()
		},
	}
}
</script>