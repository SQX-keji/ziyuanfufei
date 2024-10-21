<template>
	<view>
		<view class="wrap">
			<u-image width="100%" height="400rpx" mode="widthfix" src="../../../static/images/index/图层 6.png"></u-image>
			<view class="u-tabs-box">
				<u-tabs-swiper active-color="#5074FF" ref="tabs" :list="tabList" :current="current" @change="change"
					:is-scroll="false" swiperWidth="750"></u-tabs-swiper>
			</view>
			<swiper class="swiper-box" :current="swiperCurrent" @transition="transition"
				@animationfinish="animationfinish">
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">
						<view class="page-box bg-white padding">
							<view class="text-bold text-lg text-black margin-bottom">教程介绍</view>
							<view class="text-gray margin-bottom">公司推出的一款图像视频处理软件，适用于从事设计视频特效的
								机构，包括电视台，动画制作公司，个人后期制作工作室以及多 媒体工作室，属于层类型后期软件.</view>
							<view class="text-bold text-lg text-black margin-bottom">你能学到什么</view>
							<view class="text-gray">
								<view class="u-font-16">1.熟练使用AE软件，掌握基础特效制作方法</view>
								<view class="u-font-16">2.做出栏目包装效果，了解影视后期动画的制作技法</view>
								<view class="u-font-16">3.可在移动设备以及网页端同时观看</view>
								<view class="u-font-16">4.学完全部课程可获得完成证书</view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">
						<view class="page-box bg-white padding">
							<view class="text-bold text-orange text-lg margin-bottom flex">
								<u-image width="28rpx" height="32rpx" mode="widthfix" class="margin-right" src="../../../static/images/index/PC播放页_排行榜.png"></u-image>
								PS—插画构图基础—对角线构图
							</view>
							<view class="text-bold text-black text-lg margin-bottom">PS—插画构图基础—对角线构图</view>
							<view class="text-bold text-black text-lg margin-bottom">PS—插画构图基础—对角线构图</view>
							<view class="text-bold text-black text-lg margin-bottom">PS—插画构图基础—对角线构图</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;">
						<view class="page-box bg-white">
							<view class="comment" v-for="(res, index) in commentList" :key="res.id">
								<view class="left"><image :src="res.url" mode="aspectFill"></image></view>
								<view class="right">
									<view class="top">
										<view class="name">{{ res.name }}</view>
										<view class="like" :class="{ highlight: res.isLike }">
											<u-icon v-if="!res.isLike" name="heart" :size="30" color="#9a9a9a" @click="getLike(index)"></u-icon>
											<u-icon v-if="res.isLike" name="heart-fill" :size="30" @click="getLike(index)"></u-icon>
											<view class="num">{{ res.likeNum }}</view>
										</view>
									</view>
									<view class="bottom">
										{{ res.date }}
									</view>
									<view class="content">{{ res.contentText }}</view>
								</view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
			</swiper>
			<view class="navigation" v-if="current != 2">
				<view class="left">
					<view class="item">
						<u-image src="../../../static/images/index/收藏 拷贝.png" width="44rpx" height="44rpx"></u-image>
						<view class="text u-line-1">收藏</view>
					</view>
				</view>
				<view class="right">
					<view class="cart btn u-line-1">购买课程¥34.96</view>
					<view class="buy btn u-line-1">开通会员免费</view>
				</view>
			</view>
			<view class="bg-white padding-tb-sm padding-lr flex" v-else style="position: fixed;bottom: 0;width: 100%;">
				<!-- <u-search placeholder="发条有爱评论~" shape="square" v-model="keyword" height="80" action-text="发送"></u-search> -->
				<u-input placeholder="发条有爱评论~" placeholder-style="marginLeft: 10px" v-model="value" :type="type" :border="border" class="radius" style="background: #F1F5F8;color: #CCCCCC;" />
				<text style="line-height: 35px;margin-left: 10px;">发送</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				orderList: [
					[],
					[],
					[]
				],

				tabList: [{
						name: '详情'
					},
					{
						name: '目录'
					},
					{
						name: '评论'
					}
				],
				current: 0,
				swiperCurrent: 0,
				tabsHeight: 0,
				dx: 0,
				loadStatus: ['loadmore', 'loadmore', 'loadmore', 'loadmore'],
				commentList: [
					{
						id: 1,
						name: '欧阳诺其',
						date: '01-25',
						contentText: '在外面不管什么风吹雨打，回家依旧光芒万丈，致敬打工人',
						allReply: 0,
						likeNum: 11,
						isLike: false,
						url: 'https://cdn.uviewui.com/uview/template/niannian.jpg',
					},
					{
						id: 1,
						name: '欧阳诺其',
						date: '01-25',
						contentText: '在外面不管什么风吹雨打，回家依旧光芒万丈，致敬打工人',
						allReply: 0,
						likeNum: 11,
						isLike: false,
						url: 'https://cdn.uviewui.com/uview/template/niannian.jpg',
					},
					{
						id: 1,
						name: '欧阳诺其',
						date: '01-25',
						contentText: '在外面不管什么风吹雨打，回家依旧光芒万丈，致敬打工人',
						allReply: 0,
						likeNum: 11,
						isLike: false,
						url: 'https://cdn.uviewui.com/uview/template/niannian.jpg',
					},
				],
				value: '',
				
			};
		},
		onLoad() {
			this.getOrderList(0);
		},
		methods: {
			reachBottom() {
				// 此tab为空数据
				// if (this.current != 2) {
				// 	this.loadStatus.splice(this.current, 1, "loading")
				// 	setTimeout(() => {
				// 		this.getOrderList(this.current);
				// 	}, 1200);
				// }
			},
			// 页面数据
			getOrderList(idx) {

			},
			// 点赞
			getLike(index) {
				
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
			transition({
				detail: {
					dx
				}
			}) {
				this.$refs.tabs.setDx(dx);
			},
			animationfinish({
				detail: {
					current
				}
			}) {
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
	.navigation {
		display: flex;
		border: solid 2rpx #f2f2f2;
		background-color: #ffffff;
		padding: 10rpx 0;

		.left {
			display: flex;
			font-size: 20rpx;

			.item {
				margin: 0 30rpx;

				&.car {
					text-align: center;
					position: relative;

					.car-num {
						position: absolute;
						top: -10rpx;
						right: -10rpx;
					}
				}
			}
		}

		.right {
			flex: 1;
			display: flex;
			font-size: 28rpx;
			align-items: center;

			.btn {
				width: 150px;
				line-height: 80rpx;
				padding: 0 10rpx;
				color: #ffffff;
				text-align: center;
			}

			.cart {
				border-radius: 39px 0px 0px 39px;
				background-color: #FF5A00;
			}

			.buy {
				border-radius: 0px 39px 39px 0px;
				background-color: #5074FF;
			}
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
	// 评论
	.comment {
		display: flex;
		padding: 30rpx;
		.left {
			image {
				width: 64rpx;
				height: 64rpx;
				border-radius: 50%;
				background-color: #f2f2f2;
			}
		}
		.right {
			flex: 1;
			padding-left: 20rpx;
			font-size: 30rpx;
			.top {
				display: flex;
				justify-content: space-between;
				align-items: center;
				margin-bottom: 10rpx;
				.name {
					color: #333;
					font-weight: bold;
				}
				.like {
					display: flex;
					align-items: center;
					color: #9a9a9a;
					font-size: 26rpx;
					.num {
						margin-right: 4rpx;
						color: #9a9a9a;
					}
				}
				.highlight {
					color: #5677fc;
					.num {
						color: #5677fc;
					}
				}
			}
			.content {
				margin-top: 20rpx;
				margin-bottom: 10rpx;
			}
			
			.bottom {
				
				display: flex;
				font-size: 24rpx;
				color: #9a9a9a;
				.reply {
					color: #5677fc;
					margin-left: 10rpx;
				}
			}
		}
	}
</style>
