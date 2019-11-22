<template>
	<view class="set-up">
		<block v-for="(item, index) in setupList" :key="index">
			<view class="set-up-item u-f-jsb">
				<view class="u-f-ajc">{{item.name}}</view>
				<view class="u-f-ac">
					<template v-if="item.type === 'open'">
						<view class="open-btn" :class="[item.open? 'open' : 'unopen']">{{item.open? '已开启' : '未开启'}}</view>
					</template>
					<template v-if="item.type === 'switch'">
						<switch :checked="item.switch" class="switch" color="#12D277" @change="switchChange(index, $event)" />
					</template>
					<template v-else>
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
					{
						name: '仅WIFI下使用',
						type: 'switch',
						auth: false,
						open: false,
						switch: false,
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '切换到3G/4G网络时提醒我',
						type: 'switch',
						auth: false,
						open: false,
						switch: true,
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '给老师们好评',
						type: 'none',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '清理缓存',
						type: 'none',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '网络诊断',
						type: 'none',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '异常日志上报',
						type: 'none',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					},
					{
						name: '关于我们',
						type: 'none',
						clicktype: 'navigateTo',
						url: '../../pages/user-set-repassword/user-set-repassword'
					}
				]
			}
		},
		methods: {
			switchChange(index,e) {
				console.log(JSON.stringify(e))
				this.setupList[index].switch = e.detail.value
			}
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
.set-up-item>view:first-child{
	line-height: 90upx;
}
.set-up-item>view:last-child {
	font-size: 24upx;
	color: #D9D9D9;
}
.set-up-item .open-btn{
	color: #FFFFFF;
	padding: 0 10upx;
	font-size: 24upx;
	line-height: 1.8;
	margin-right: 20upx;
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
.switch {
	transform: scale(0.8);
	margin-left: 5px;
	
}
.uni-switch-wrapper .uni-switch-input-checked{
	background: aqua !important;
}
</style>
