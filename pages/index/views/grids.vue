<template>
	<view style="margin: 0 20rpx;">
		<view class="content">
			<block v-for="(item,index) in tables" :key="index">
				<view>
					<text class="ticket">{{item.name}}</text>
					<text class="lab">{{item.lable}}</text>
				</view>
			</block>
		</view>
	</view>
</template>

<script>
	export default{
		data() {
			return {
				tables : [
					{
						"kid" : "100001",
						"name" : "出境游",
						"lable" : "走遍全球"
					},
					{
						"kid" : "100002",
						"name" : "国内游",
						"lable" : "精选路线"
					},
					{
						"kid" : "100003",
						"name" : "周边游",
						"lable" : "暑假红包"
					},
					{
						"kid" : "100004",
						"name" : "精选购",
						"lable" : "免税预购"
					},
					{
						"kid" : "100005",
						"name" : "签证|签注",
						"lable" : "走遍全球"
					},
					{
						"kid" : "100006",
						"name" : "会员优惠",
						"lable" : "签到"
					},
					{
						"kid" : "100007",
						"name" : "每日福利",
						"lable" : "暑假红包"
					},
					{
						"kid" : "100009",
						"name" : "全部",
						"lable" : "更多推荐"
					}
				]
			}
		}
	}
</script>

<style scoped>
	.content{
		display:flex;/* 里面的每一个都要并排 */
		flex-wrap: nowrap;/* 若一排排不下时向下排 */
		width: 100%;/* 100/4=25 */
		-webkit-flex-wrap:wrap;
		overflow: hidden;
		border: 1rpx solid #55aaff;/* 总边框 */
		border-radius:10rpx;
	}
	.content view{
		width: 25%;/* 25*4个格子=100 */
		flex-direction: column;
		align-items: center;/* 两行文字垂直居中 */
		display: flex;
		box-sizing: border-box;
		padding: 20rpx 0;/* 撑开边框 */
	}
	.content view:nth-child(2){border-left: 1rpx solid #b93dee; border-right:1rpx solid #f00;}/* 第1排的第2个的左右都有边框 */
	.content view:nth-child(6){border-left: 1rpx solid #ffaaff; border-right:1rpx solid #211aee;}/* 第2行的第2个的左右都有边框，但是后面的会覆盖前面的样式 */
	.content view:nth-child(3){border-right:1rpx solid #5500ff;}/* 第1排的第3个有右边框 */
	.content view:nth-child(7){border-right:1rpx solid #aa0000;}/* 第2排的第3个有右边框 */
	.content view:nth-child(-n+4){border-bottom:1rpx solid #ff00ff;}/* 前4个，也就是第1排的4个都有下边框 */
	.ticket{font-size: 30rpx;color:#333333;font-weight: bold;}
	.lab{font-size:24rpx;color: #686868;margin-top:4rpx;}
</style>
