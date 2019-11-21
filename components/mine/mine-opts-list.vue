<template>
	<view class="mine-list-item u-f-jsb">
		<view class="u-f-ac">
			<view class="icon iconfont u-f-ajc" :class="['icon-'+item.icon]"></view>
			{{item.name}}
		</view>
		<view class="icon iconfont icon-jiantouyou"></view>
	</view>
</template>

<script>
	export default {
		props: {
			item: Object,
			index: Number
		},
		methods: {
			
		}
	}
</script>

<style scoped>
	.mine-list-item{
		padding: 8upx 30upx;
		background: #FFFFFF;
		border-bottom: 1upx solid rgba(0,0,0,0.1);
		font-size: 32upx;
		color: #333333;
	}
	.mine-list-item>view:first-child>view{
		margin-right: 8upx;
		font-size: 28upx;
	}
	.mine-list-item>view:last-child {
		color: #D9D9D9;
	}
</style>
