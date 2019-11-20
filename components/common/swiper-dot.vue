<template>
	<view class="dot-main">
		<view :class="['dot-item',current==index?'active':'']" v-for="(item,index) in list" :key="index"></view>
	</view>
</template>

<script>
	export default {
		props: [ 'list','current']
	}
</script>

<style scoped>
	.dot-main {
		width: 100vw;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.dot-item {
		width: 10upx;
		height: 10upx;
		background: #FFFFFF;
		margin: 0 6upx;
		box-sizing: border-box;
		border-radius: 100%;
	}
	.active {
		width: 40upx;
		border-radius: 4upx;
	}
</style>
