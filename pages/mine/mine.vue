<template>
	<view class="body">
		<!-- 头部 -->
		<view class="mine-head u-f-jsb">
			<view class="u-f">
				<image src="../../static/demo/1.jpg" mode="widthFix" lazy-load></image>
				<view class="user-info">
					<view>学员小白</view>
					<view>编辑个人资料</view>
				</view>
			</view>
			<view class="icon iconfont icon-jiantouyou"></view>
		</view>
		<!-- 头部导航 -->
		<view class="mine-head-nav u-f-jsb">
			<view class="mine-head-nav-item u-f-column">
				<view class="icon iconfont icon-zhengshu u-f-ajc"></view>
				安博证书
			</view>
			<view class="mine-head-nav-item">
				<view class="icon iconfont icon-riqi u-f-ajc"></view>
				课程日历
			</view>
			<view class="mine-head-nav-item">
				<view class="icon iconfont icon-collect u-f-ajc"></view>
				我的收藏
			</view>
		</view>
		<!-- 功能列表 -->
		<view class="mine-list">
			<block v-for="(item, index) in optsList" :key="index">
				<mine-opts-list :item="item" :index="index"></mine-opts-list>
			</block>
		</view>
	</view>
</template>

<script>
	import MineOptsList from '@/components/mine/mine-opts-list.vue'
	
	export default {
		components: {
			MineOptsList
		},
		data() {
			return {
				optsList: [
					{
						name: '我的订单',
						icon: 'dd',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '我的消息',
						icon: 'xiaoxi',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '我的协议',
						icon: 'xieyi',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '优惠券',
						icon: 'youhuiquan',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '常见问题',
						icon: 'question-circle',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '意见反馈',
						icon: 'fankui',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
				]
			}
		},
		onNavigationBarButtonTap(e) {
			console.log(JSON.stringify(e))
			if(e.index === 0) {
				// 跳转到配置页面
				uni.navigateTo({
					url: '../set-up/set-up'
				});
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
.body{ 
	background: #FBFBFB;
}
.mine-head {
	background: #FF3E5C;
	height: 300upx;
	border-radius: 0 0 60upx 60upx;
	color: #FFFFFF;
	padding: 0 30upx;
}
.mine-head>view {
	margin-top: 50upx; 
}
.mine-head>view:first-child>image{
	width: 100upx ;
	height: 100upx;
	border-radius: 100%;
	margin-right: 10upx;
}
.mine-head .user-info>view:first-child {
	font-size: 30upx;
	font-weight: bold;
}
.mine-head .user-info>view:last-child {
	font-size: 26upx;
	color: #FBFBFB;
}
/* 头部导航 */
.mine-head-nav {
	background: #FFFFFF;
	border-radius: 5upx;
	width: 500upx;
	margin: -100upx auto 0;
	padding: 40upx 50upx;
	box-shadow: 0 10upx 10upx #D8D8D8;
}
.mine-head-nav-item {
	font-size: 24upx;
	color: #333333;
}
.mine-head-nav-item>view{
	color: #B9B9B9;
	font-size: 45upx;
}
/* 功能列表 */
.mine-list{
	margin: 40upx 20upx;
	border-radius: 5upx;
	border-top: 1upx solid rgba(0,0,0,0.1);
	border-left: 1upx solid rgba(0,0,0,0.1);
	border-right: 1upx solid rgba(0,0,0,0.1);
}

</style>
