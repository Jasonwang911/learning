<template>
	<view class="recommend-lesson-item">
		<view>{{item.title}}</view>
		<view>{{item.desc}}</view>
		<view class="u-f-jsb">
			<view class="u-f-ac">
				<image :src="item.userpic" mode="widthFix" lazy-load></image>
				{{item.username}}
			</view>
			<view class="u-f-ajc">￥{{item.price}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			item: Object,
			index: Number
		}
	}
</script>

<style scoped>
	.recommend-lesson-item {
		width: 300upx;
		background: #FFFFFF;
		font-size: 26upx;
		border-radius: 5upx;
		box-shadow: 0 0 18upx #D9D9D9;
		display: inline-block;
		margin-right: 32upx;
	}
	.recommend-lesson-item>view:nth-of-type(1) {
		height: 105upx;
		color: #333333;
		line-height: 40upx;
		font-size: 24upx;
		margin: 20upx 20upx 0;
		display:block;
		white-space:normal;
	}
	.recommend-lesson-item>view:nth-of-type(2) {
		font-size: 24upx;
		color: #999999;
		line-height: 40upx;
		padding: 0 20upx;
		margin: 20upx 0;
	}
	.recommend-lesson-item>view:nth-of-type(3) {
		border-top: 1upx solid rgba(0,0,0,0.1);
		padding: 20upx;
	}
	.recommend-lesson-item>view:nth-of-type(3)>view:first-child{
		font-size: 24upx;
		color: #666666;
	}
	.recommend-lesson-item>view:nth-of-type(3)>view:first-child>image {
		width: 60upx;
		height: 60upx;
		border-radius: 100%;
		margin-right: 8upx;
	}
	.recommend-lesson-item>view:nth-of-type(3)>view:last-child{
		font-size: 30upx;
		color:#F34164;
	}
</style>
