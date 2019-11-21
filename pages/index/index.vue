<template>
	<view>
		<!-- 自定义导航栏 -->
		<index-nav-bar></index-nav-bar>
		<!-- 头部导航 -->
		<swiper-nav :tabBars="topicNav" :tabIndex="topicNavIndex" @tabtap="tabtap"></swiper-nav>
		<!-- swiper -->
		<view class="swiper">
			<swiper
				class="topic-swiper" 
				:interval="3000" 
				:autoplay="true"
				:duration="1000"
				@change="changeSwiper">
				<swiper-item v-for="(item, index) in swiperList" :key="index">
					<view class="swiper-item">
						<image :src="item.url" mode="scaleToFill" lazy-load></image>
					</view>
				</swiper-item>
			</swiper>
			<swiper-dot class="dot" :current="currentSwiper" :list="swiperList"></swiper-dot>
		</view>
		<!-- 导航按钮 -->
		<view class="nav-btn u-f-jsb">
			<block v-for="(item, index) in navBtnList" :key="index">
				<view class="nav-btn-item u-f-column">
					<view class="icon iconfont u-f-ajc" :class="'icon-'+item.icon" :style="{background: item.color}"></view>
					<view class="u-f-ajc">{{item.name}}</view>
				</view>
			</block>
		</view>
		<view class="body">
			<!-- 推荐课 -->
			<view class="recommend-lesson">
				<view class="recommend-lesson-head u-f-jsb u-f-ajc">
					<view>推荐课</view>
					<view>more</view>
				</view>
				<view class="recommend-lesson-list uni-tab-bar">
					<scroll-view scroll-x class="uni-swiper-tab">
						<block v-for="(item, index) in recommendList" :key="index">
							<lesson-item :item="item" :index="index"></lesson-item>
						</block>
					</scroll-view>
				</view>
			</view>
			<view class="recommend-lesson">
				<view class="recommend-lesson-head u-f-jsb u-f-ajc">
					<view>化学课</view>
					<view>more</view>
				</view>
				<view class="recommend-lesson-list uni-tab-bar">
					<scroll-view scroll-x class="uni-swiper-tab">
						<block v-for="(item, index) in recommendList" :key="index">
							<lesson-item :item="item" :index="index"></lesson-item>
						</block>
					</scroll-view>
				</view>
			</view>
		</view>
		
		
	</view>
</template>

<script>
	import IndexNavBar from '@/components/index/index-nav-bar.vue'
	import SwiperNav from '@/components/common/swiper-nav.vue'
	import swiperDot from "@/components/common/swiper-dot.vue"
	import LessonItem from '@/components/index/lesson-item.vue'
	
	export default {
		components: {
			IndexNavBar,
			SwiperNav,
			swiperDot,
			LessonItem
		},
		data() {
			return {
				topicNavIndex: 0,
				topicNav: [
					{
						id: 1,
						name: '兢才修业'
					},
					{
						id: 2,
						name: '新干线'
					},
					{
						id: 3,
						name: '人众人'
					},
					{
						id: 4,
						name: '寰宇利人'
					},
					{
						id: 5,
						name: '大成教育'
					},
					{
						id: 6,
						name: '大成教育'
					},
					{
						id: 7,
						name: '大成教育'
					}
				],
				currentSwiper: 0,
				swiperList: [
					{
						id: 1,
						url: '../../static/demo/34.jpg'
					},
					{
						id: 2,
						url: '../../static/demo/35.jpg'
					},
					{
						id: 3,
						url: '../../static/demo/36.jpg'
					},
				],
				navBtnList: [
					{
						icon: 'dashaxiaoqudizhi01',
						color: '#FF8D39',
						name: '校区'
					},
					{
						icon: 'erji',
						color: '#67C70B',
						name: '试听'
					},
					{
						icon: 'tianchongxing-',
						color: '#2EA0F0',
						name: 'K12'
					},
					{
						icon: 'xuexi',
						color: '#FDB730',
						name: '名师'
					},
					{
						icon: 'youhuiquan',
						color: '#00C46A',
						name: '优惠'
					}
				],
				recommendList: [
					{
						id: 1,
						title: '高三数学腾飞班级（3星）录播班型外教周一周三',
						desc: '基础巩固，培养学习兴趣',
						userpic: '../../static/demo/1.jpg',
						username: '雏老师',
						price: 1500
					},
					{
						id: 1,
						title: '高三数学腾飞班级（5星）直播班型',
						desc: '保送清华/北大',
						userpic: '../../static/demo/3.jpg',
						username: '白老师',
						price: 700
					},
					{
						id: 1,
						title: '高三数学腾飞班级（3星）录播班型外教周一周三',
						desc: '基础巩固，培养学习兴趣',
						userpic: '../../static/demo/2.jpg',
						username: '雏老师',
						price: 1500
					},
					{
						id: 1,
						title: '高三数学腾飞班级（3星）录播班型外教周一周三',
						desc: '基础巩固，培养学习兴趣',
						userpic: '../../static/demo/3.jpg',
						username: '雏老师',
						price: 1500
					}
				]
			}
		},
		onLoad() {

		},
		methods: {
			tabtap(index) {
				this.topicNavIndex = index
			},
			changeSwiper(e) {
				this.currentSwiper = e.detail.current;
			}
		}
	}
</script>

<style scoped>
.swiper{
	margin: 20upx 0;
}
.topic-swiper{
	padding: 0 20upx 20upx 20upx;
}
.swiper-item{
	border-radius: 10upx;
	margin: 0 20upx;
	overflow: hidden;
}
.topic-swiper image{
	width: 100%;
	height: 300upx;
	border-radius: 10upx;
}
.swiper{
	position: relative;
	z-index: 1;
}
.dot{
	width: 100%;
	position: absolute;
	bottom: 60upx;
	z-index: 10;
}
/* 导航按钮样式 */
.nav-btn{
	padding: 0 40upx 40upx;
	box-shadow: 0 10upx 10upx #D9D9D9;
}
.nav-btn-item>view:first-child{
	width: 88upx;
	height: 88upx;
	font-size: 50upx;
	color: #FFFFFF;
	background:  #FF8D39;
	border-radius: 30upx;
}
.nav-btn-item>view:last-child{
	color: #333333;
	font-size: 24upx;
	line-height: 56upx;
}
/* .body{
	background: #FBFBFB;
} */
/* 推荐课 */
.recommend-lesson{
	padding: 15upx 40upx 15upx;
}
.uni-swiper-tab{
	height: auto !important;
	border-bottom: none !important;
}
.recommend-lesson-head {
	padding: 15upx 0;
}
.recommend-lesson-head>view:first-child{
	font-size: 38upx;
	font-weight: bold;
	color: #333333;
}
.recommend-lesson-head>view:last-child{
	font-size: 24upx;
	color: #999999;
}
</style>
