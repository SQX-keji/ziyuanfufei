<template>
	<view>
		<view class="wrap">
			<view class="u-tabs-box">
				<u-tabs-swiper activeColor="#f29100" ref="tabs" :list="tabList" :current="current" @change="change" :is-scroll="false" swiperWidth="750"></u-tabs-swiper>
			</view>
			<swiper class="swiper-box" :current="swiperCurrent" @transition="transition" @animationfinish="animationfinish">
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">
						<!-- <view class="centre">
							<image src="../../static/images/learn/空状态.png" mode=""></image>
							<view class="tips">
								暂无课程
							</view>
							<view class="btn">立即购买</view>
						</view> -->
						<view class="page-box">
							<view class="order"v-for="(item, index) in courseList" :key="index" @click="goCourse(item.id)">
								<view class="item" >
									<view class="left"><image :src="item.image" mode="aspectFill"></image></view>
									<view class="content flex flex-direction justify-between">
										<view class="flex flex-direction justify-between flex-sub">
											<view class="title u-line-2">{{ item.title }}</view>
											<view class="buttom margin-top">
												<view class="price">
													￥{{ priceInt(item.price) }}
												</view>
												<view class="number">学习进度{{ item.progress }}</view>
											</view>
										</view>
										<view class="flex margin-top-sm">
											<view>
												<u-avatar class="head" size="44" src="../../static/images/learn/图层 10.png"></u-avatar>
												<u-avatar class="head1" size="44" src="../../static/images/learn/图层 10.png"></u-avatar>
												<u-avatar class="head2" size="44" src="../../static/images/learn/图层 10.png"></u-avatar>
											</view>
											<view class="text-gray number">{{item.number}}人已观看</view>
										</view>
									</view>
								</view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">
						<view class="page-box">
							<view class="centre">
								<image src="../../static/images/learn/空状态.png" mode=""></image>
								<view class="tips">
									暂无课程
								</view>
								<view class="btn">立即购买</view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;">
						<view class="page-box">
							<view class="centre">
								<image src="../../static/images/learn/空状态.png" mode=""></image>
								<view class="tips">
									暂无课程
								</view>
								<view class="btn">立即购买</view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			orderList: [[], [], []],
			tabList: [
				{
					name: '最近学习'
				},
				{
					name: '已购课程'
				},
				{
					name: '收藏课程'
				}
			],
			current: 0,
			swiperCurrent: 0,
			tabsHeight: 0,
			dx: 0,
			loadStatus: ['loadmore','loadmore','loadmore','loadmore'],
			
			courseList: [
				{
					image: "../../static/images/learn/图层 6.png",
					title: "【美团资深设计师】带你学习UI设计",
					price: "129",
					progress: "30%",
					user:[
						"../../static/images/learn/图层 10.png",
						"../../static/images/learn/图层 10.png",
						"../../static/images/learn/图层 10.png",
					],
					number: "1268",
					url: ''
				},
				{
					image: "../../static/images/learn/图层 6.png",
					title: "【美团资深设计师】带你学习UI设计",
					price: "129",
					progress: "30%",
					user:[
						"../../static/images/learn/图层 10.png",
						"../../static/images/learn/图层 10.png",
						"../../static/images/learn/图层 10.png",
					],
					number: "1268"
				},
				{
					image: "../../static/images/learn/图层 6.png",
					title: "【美团资深设计师】带你学习UI设计",
					price: "129",
					progress: "30%",
					user:[
						"../../static/images/learn/图层 10.png",
						"../../static/images/learn/图层 10.png",
						"../../static/images/learn/图层 10.png",
					],
					number: "1268"
				},
				{
					image: "../../static/images/learn/图层 6.png",
					title: "【美团资深设计师】带你学习UI设计",
					price: "129",
					progress: "30%",
					user:[
						"../../static/images/learn/图层 10.png",
						"../../static/images/learn/图层 10.png",
						"../../static/images/learn/图层 10.png",
					],
					number: "1268"
				}
				
			]
		};
	},
	onLoad() {
		this.getOrderList(0);
		this.getOrderList(1);
		this.getOrderList(3);
	},
	computed: {
		// 价格小数
		priceDecimal() {
			return val => {
				if (val !== parseInt(val)) return val.slice(-2);
				else return '00';
			};
		},
		// 价格整数
		priceInt() {
			return val => {
				if (val !== parseInt(val)) return val.split('.')[0];
				else return val;
			};
		}
	},
	methods: {
		reachBottom() {
			// 此tab为空数据
			if(this.current != 2) {
				this.loadStatus.splice(this.current,1,"loading")
				setTimeout(() => {
					this.getOrderList(this.current);
				}, 1200);
			}
		},
		// 页面数据
		getOrderList(idx) {
			
		},
		// 总价
		totalPrice(item) {
			let price = 0;
			item.map(val => {
				price += parseFloat(val.price);
			});
			return price.toFixed(2);
		},
		// 总件数
		totalNum(item) {
			let num = 0;
			item.map(val => {
				num += val.number;
			});
			return num;
		},
		// tab栏切换
		change(index) {
			this.swiperCurrent = index;
			this.getOrderList(index);
		},
		transition({ detail: { dx } }) {
			this.$refs.tabs.setDx(dx);
		},
		animationfinish({ detail: { current } }) {
			this.$refs.tabs.setFinishCurrent(current);
			this.swiperCurrent = current;
			this.current = current;
		}
	}
};
</script>

<style>
/* #ifndef H5 */
page {
	height: 100%;
	background-color: #f2f2f2;
}
/* #endif */
</style>

<style lang="scss" scoped>
.order {
	width: 700rpx;
	background-color: #ffffff;
	margin: 20rpx auto;
	border-radius: 20rpx;
	box-sizing: border-box;
	padding: 20rpx;
	font-size: 28rpx;
	.top {
		display: flex;
		justify-content: space-between;
		.left {
			display: flex;
			align-items: center;
			.store {
				margin: 0 10rpx;
				font-size: 32rpx;
				font-weight: bold;
			}
		}
		.right {
			color: $u-type-warning-dark;
		}
	}
	.item {
		display: flex;
		.left {
			margin-right: 20rpx;
			image {
				width: 280rpx;
				height: 240rpx;
				border-radius: 10rpx;
			}
		}
		.content {
			.title {
				font-size: 16px;
				line-height: 50rpx;
				font-weight: bold;
			}
			.buttom {
				display: flex;
				justify-content: space-between;
				border-bottom: 1px solid #E6E6E6;
				
				.price {
					font-size: 18px;
					font-weight: bold;
					color: #FF3838;
				}
				
				.number {
					font-size: 14px;
					color: #999999;
					line-height: 24px;
				}
			}
			.head1 {
				position: relative;
				left: -5px;
			}
			.head2 {
				position: relative;
				left: -10px;
			}
			.number {
				line-height: 50rpx;
			}
		}
		
	}
	.total {
		margin-top: 20rpx;
		text-align: right;
		font-size: 24rpx;
		.total-price {
			font-size: 32rpx;
		}
	}
	.bottom {
		display: flex;
		margin-top: 40rpx;
		padding: 0 10rpx;
		justify-content: space-between;
		align-items: center;
		.btn {
			line-height: 52rpx;
			width: 160rpx;
			border-radius: 26rpx;
			border: 2rpx solid $u-border-color;
			font-size: 26rpx;
			text-align: center;
			color: $u-type-info-dark;
		}
		.evaluate {
			color: $u-type-warning-dark;
			border-color: $u-type-warning-dark;
		}
	}
}
.centre {
	text-align: center;
	margin: 200rpx auto;
	font-size: 32rpx;
	image {
		width: 360rpx;
		height: 360rpx;
		// margin-bottom: 20rpx;
		margin: 0 auto 20rpx;
		border: 1px dotted #000000;
	}
	.tips {
		font-size: 40rpx;
		color: #5074FF;
		margin-top: 20rpx;
	}
	.btn {
		margin: 80rpx auto;
		width: 600rpx;
		border-radius: 32rpx;
		line-height: 90rpx;
		color: #ffffff;
		font-size: 34rpx;
		background: #5074FF;
	}
}
.wrap {
	display: flex;
	flex-direction: column;
	height: calc(100vh - var(--window-top));
	width: 100%;
}
.swiper-box {
	flex: 1;
}
.swiper-item {
	height: 100%;
}
</style>
