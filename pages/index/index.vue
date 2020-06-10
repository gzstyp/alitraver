<template>
	<view>
		<search></search>
		<slideshow></slideshow>
		<travels></travels>
		<grids></grids>
	</view>
</template>

<script>
	import search from './views/search';
	import slideshow from './views/slideshow.vue';
	import travels from './views/travels.vue';
	import grids from './views/grids.vue';
	export default {
		components:{
			search,
			slideshow,
			travels,
			grids
		},
		data() {
			return {
				title: 'Hello'
			}
		},
		methods: {

		}
	}
</script>

<style scoped>
	
</style>
