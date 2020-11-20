<template>
	<view>
		<scroll-view scroll-x="true" class="scroll" scroll-with-animation="true">
			<view>
				<block v-for="(item,index) in sliders" :key="index">
					<view @click="nav(index,item.nav)" class="list-content" :class="{activeCurrent:index==num}">
						<view>
							<text :class="{activeName:index==num}" class="con-text-name">{{item.name}}</text>
						</view>
						<view>
							<text :class="{activeTitle:index==num}" class="con-text-title">{{item.title}}</text>
						</view>
					</view>
				</block>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default{
		data() {
			return {
				num : 0,
				sliders : [
					{
						"kid":"100001",
						"nav":"nav",
						"name":"推荐",
						"title":"猜你喜欢"
					},
					{
						"kid":"100002",
						"nav":"nav",
						"name":"好景点",
						"title":"周末放空"
					},
					{
						"kid":"100003",
						"nav":"nav",
						"name":"人文",
						"title":"文化之旅"
					},
					{
						"kid":"100004",
						"nav":"nav",
						"name":"海岛",
						"title":"阳光与沙滩"
					},
					{
						"kid":"100005",
						"nav":"nav",
						"name":"自由行",
						"title":"超值精选"
					},
					{
						"kid":"100006",
						"nav":"nav",
						"name":"情侣",
						"title":"别样的浪漫"
					},
					{
						"kid":"100007",
						"nav":"nav",
						"name":"网红",
						"title":"最火打地卡"
					}
				]
			}
		},
		methods:{
			nav : function(index,nav){
				this.num = index;
			}
		}
	}
</script>

<style scoped>
	.scroll{
		white-space: nowrap;/* 左右滚动的关键 */
		width: 100%;
		position:absolute;
		left: 0;
		right: 0;
		background:#FFFFFF;
		padding: 20rpx 0;
	}
	.list-content{
		width: 180rpx;
		display: inline-block;
		text-align: center;
	}
	.activeCurrent{
		background-image: linear-gradient(to right,#ccffff 0%,#ffcc00 100%);
		border-top-right-radius: 50rpx;
	}
	.activeName{
		color:#292c33 !important;
		font-size:31rpx !important;
	}
	.activeTitle{
		color:#292c33 !important;
		font-size:23rpx !important;
	}
	.con-text-name{
		color: #292C33;
		font-size: 30rpx;
		font-weight: bold;
	}
	.con-text-title{
		color: #9ea0a5;
		font-size: 23rpx;
	}
</style>
