<template>
	<!-- 搜索 -->
	<view class="search-content">
		<view class="search-code">
			<image src="../../../static/images/icon/scan_normal.svg" mode="widthFix"></image>
		</view>
		<view class="search">
			<image src="../../../static/images/icon/search.svg" mode="widthFix" class="search-img"></image>
			<input type="text" placeholder="请输入关键字" disabled/>
		</view>
		<view class="search-code">
			<image src="../../../static/images/icon/msg.svg" mode="widthFix"></image>	
		</view>
	</view>
</template>

<script>
	export default{
		name:"search",
		data() {
			return {
				"key": 0
			}
		}
	}
</script>

<style scoped>
	.search-code image{width: 50rpx;height: 50rpx;}
	.search-code{width: 50rpx;height: 50rpx;padding: 0 15rpx;}
	/* 搜索的图标和input输入框是在一排的,所以用-->使用flex能并排;然后定定位置就达到我们想要的效果 */
	.search-img{margin: auto 0 auto 20rpx;width: 50rpx;height: 50rpx;}
	.search{
		height: 70rpx;
		line-height: 70rpx;
		width: 100%;
		display: flex;/* 使用flex能并排.flex可以排在一排 */
		flex-direction: flex;
		background: #fff7d4;
		border-top-left-radius:50rpx;/* 圆角-左上角样式 */
		border-bottom-left-radius: 50rpx;/* 圆角-左下角样式 */
		border-bottom-right-radius: 50rpx;/* 圆角-右下角样式 */
	}
	.search input{
		height: 70rpx;
		line-height: 70rpx;
		width: 100%;
		font-size: 30rpx;
		color:#666666;
	}
	/* 让3个元素排在1排!!! */
	.search-content{
		display: flex;
		justify-content:space-between;/* 向两边拍版 */
		height:70rpx;
		align-items: center;/* 让3个元素垂直居中 */
		background:linear-gradient(to top,#ffe566 10%,#ffd300 100%);/* 渐变,从下到上的渐变 */
		padding: 30rpx 0;
	}
</style>
