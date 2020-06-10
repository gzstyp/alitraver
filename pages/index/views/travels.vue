<template>
	<view class="ticket">
		<block v-for="(item,index) in tickets" :key="index">
			<view>
				<image :src="item.image" mode="widthFix"></image>
				<text>{{item.name}}</text>
			</view>
		</block>
	</view>
</template>

<script>
	export default {
		name : "ticket",
		data() {
			return {
				tickets : [
					{
						"kid":"10001",
						"name":"机票",
						"image":"../../static/images/icon/plane.svg",
					},
					{
						"kid":"10002",
						"name":"酒店",
						"image":"../../static/images/icon/hotel.svg",
					},
					{
						"kid":"10003",
						"name":"火车票",
						"image":"../../static/images/icon/train_ticket.svg",
					},
					{
						"kid":"10004",
						"name":"汽车票",
						"image":"../../static/images/icon/automobile.svg",
					},
					{
						"kid":"10005",
						"name":"门票",
						"image":"../../static/images/icon/tickets.svg",
					}
				]
			}
		}
	}
</script>

<style scoped>
	/* 外层样式 */
	.ticket{
		display: flex;/* 并排排起 */
		justify-content: space-around;/* 间距相等 */
		text-align: center;/* 文字和图片居中显示 */
		margin: 30rpx 0;/* 外边距 */
	}
	.ticket image{width:60rpx;height:60rpx;}
	.ticket text{
		font-size: 30rpx;
		display: block;/* 设置文字和图片在并排显示 */
	}
</style>
