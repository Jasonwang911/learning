<template>
	<view class="set-up">
		<block v-for="(item, index) in setupList" :key="index">
			<view class="set-up-item u-f-jsb">
				<view class="u-f-ajc">{{item.name}}</view>
				<view class="u-f-ac">
					<template v-if="item.type === 'open'">
						<view class="open-btn" :class="[item.open? 'open' : 'unopen']">{{item.open? '已开启' : '未开启'}}</view>
					</template>
					<template v-else="item.">
						<view v-if="item.type === 'auth'">{{item.auth?'已认证': '未认证'}}</view>
						<view class="icon iconfont icon-jiantouyou"></view>
					</template>
				</view>
				
			</view>
		</block>
		
		<button type="primary">退出当前账号</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				setupList: [
					{
						name: '收货地址',
						type: 'none',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '声纹认证',
						type: 'auth',
						auth: false,
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '新消息/系统通知提醒',
						type: 'open',
						auth: false,
						open: false,
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
.set-up{
	padding: 0 20upx;
}
.set-up-item {
	border-bottom: 1upx solid rgba(0,0,0,0.1);
	font-size: 28upx;
	color: #333333;
}
.set-up-item>view:last-child {
	font-size: 24upx;
	color: #D9D9D9;
	padding: 16upx 0; 
}
.set-up-item .open-btn{
	
	color: #FFFFFF;
	padding: 0 10upx;
	font-size: 20upx;
	line-height: 1.8;
}
.set-up-item .open {
	background: #FF385D;
}
.set-up-item .unopen {
	background: #12D277;
}
.set-up button {
	background: #FF385D;
	margin: 50upx 20upx;
	font-size: 30upx;
	line-height: 90upx;
}
</style>
