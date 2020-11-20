<template>
	<view>
		<search></search>
		<slideshow></slideshow>
		<travels></travels>
		<grids></grids>
		<Horizontal id="boxFixed" :class="{'is_flxed' : isFlxed}"></Horizontal>
		<view style="height:2000rpx;"></view>
	</view>
</template>

<script>
	import search from './views/search';
	import slideshow from './views/slideshow.vue';
	import travels from './views/travels.vue';
	import grids from './views/grids.vue';
	import Horizontal from './views/horizontal.vue';
	export default {
		components:{
			search,
			slideshow,
			travels,
			grids,
			Horizontal
		},
		data() {
			return {
				isFlxed : false,
				rect : '',
				menutop : ''
			}
		},
		/* 微信小程序的方法 */
		onLoad(){
			var query = wx.createSelectorQuery();
			query.select('#boxFixed').boundingClientRect();
			query.exec((res)=>{
				console.info(res);
				/* if(res != null && res.length > 0){
					this.menuTop = res[0].top;
				} */
			});
		},
		/* 页面监听滚动 */
		onPageScroll(e){
			this.rect = e.scrollTop;
		},
		/* 计算属性,它是时刻都在监听的,只要数据变化,计算属性就会重新执行 */
		computed:{
			/* 滑动组件置顶,一定要指定方法名称(函数名称),值随便取 */
			namepage(){
				var _this = this;
				if(_this.rect > _this.menutop){
					_this.isFlxed = true;
				}else{
					_this.isFlxed = false;
				}
			}
		}
	}
</script>

<style scoped>
	/* 原理是默认是隐藏的,当到某个值时就显示,左、上、右都设置为0 */
	.is_flxed{
		position:fixed;/* 固定定位 */
		left: 0;
		top: 0;
		right: 0;
	}
</style>
