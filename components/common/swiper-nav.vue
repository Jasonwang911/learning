<template>
	<view class="uni-tab-bar">
		<scroll-view scroll-x class="uni-swiper-tab" :style="scrollStyle">
			<block v-for="(tab,index) in tabBars" :key="tab.id">
				<view class="swiper-tab-list" :class="tabIndex==index ? 'active' : ''" @tap="tabtap(index)" :style="scrollItemStyle">
					{{tab.name}} {{tab.num?tab.num:''}}
					<view class="swiper-tap-line"></view>
				</view>
			</block>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		props: {
			tabBars: Array,
			tabIndex: Number,
			scrollStyle: {
				type: String,
				default: ''
			},
			scrollItemStyle: {
				type: String,
				default: ''
			}
		},
		methods: {
			tabtap(index) {
				this.$emit('tabtap' ,index)
			}
		}
	}
</script>

<style scoped>
.swiper-tab-list {
	padding: 0 20upx !important;
	width: auto !important;
}
.uni-swiper-tab {
	border-bottom: none !important;
}
.swiper-tab-list{
	color: #969696;
	font-size: 24upx;
}
.uni-swiper-tab .active{
	color: #333333;
	font-weight: bold;
	font-size: 32upx;
}
.active .swiper-tap-line{
	width: 100%;
	height: 18upx;
	margin: -24upx auto;
	border-radius: 5upx;
	background:linear-gradient(-90deg,rgba(243,63,100,1) 0%,rgba(255,155,101,1) 100%);
}
</style>
