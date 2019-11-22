<template>
	<view>
		<uni-nav-bar :fixed="true" :border="false" :statusBar="statusBar" :rightSelect="true">
			<!-- 左边 -->
			<block slot="left">
				<view class="nav-left u-f-ajc">
					初二
					<view class="icon iconfont icon-arrowDown"></view>
				</view>
			</block>
			<!-- 中间 -->
			<block>
				<view class="nav-tab-bar u-f-ajc">
					<image src="../../static/common/logo.png" mode="widthFix" lazy-load></image>
				</view>
			</block>
			<!-- 右边 -->
			<block slot="right">
				<view class="nav-right u-f-ajc">
					长沙
					<view class="icon iconfont icon-arrowDown"></view>
				</view>
			</block>
		</uni-nav-bar>
	</view>
</template>

<script>
	import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
	
	export default {
		components: {
			uniNavBar
		},
		data() {
			return {
				// #ifndef MP-WEIXIN
				statusBar: true,
				// #endif
			}
		}
	}
</script>

<style scoped>
	.nav-left{
		color: #333333;
		width: 120upx;
		font-size: 32upx;
		font-weight: bold;
	}
	.nav-left>view{
		font-size: 26upx;
		margin-left: 6upx;
		font-weight: normal;
	}
	.nav-tab-bar{
		width: 100%;
		margin-left: -20upx;
	}
	.nav-tab-bar image {
		width: 80upx;
	}
	.nav-right{
		font-size: 24upx;
	}
	.nav-right>view{
		font-size: 14upx;
		margin-left: 8upx;
	}
</style>
