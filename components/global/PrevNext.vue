<template>
	<div class="lg:flex justify-between text-lg text-green-500">
		<NuxtLink 
			v-if="prev" 
			:to="prev.slug" 
		>
			<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"
				class="inline-flex items-center h-4 w-4 -mt-1">
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 19l-7-7 7-7m8 14l-7-7 7-7" />
			</svg>
			{{ prev.title }}  
		</NuxtLink> 
		
		<NuxtLink 
			v-if="next" 
			:to="next.slug" 
		>
		{{ next.title }}  
			<svg class="h-4 w-4 inline-flex items-center -mt-1" fill="none" stroke="currentColor" viewBox="0 0 24 24"
				xmlns="http://www.w3.org/2000/svg">
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
					d="M13 5l7 7-7 7M5 5l7 7-7 7">
				</path>
			</svg> 
		</NuxtLink>
	</div>
</template>

<script>
export default {
	props: {
		prev: {
			type: Object,
			default: () => null
		},
		next: {
			type: Object,
			default: () => null
		}
	}
}
</script>