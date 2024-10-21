<template>
	<view>
		<view class="bg-white u-flex user-box u-p-l-30 u-p-t-30 u-p-b-30">
			<view class="u-m-r-10">
				<u-avatar :src="pic" size="100"></u-avatar>
			</view>
			<view class="u-flex-1">
				<view class="u-font-18 u-p-b-20 text-bold">佛系小草莓</view>
				<view class="u-font-14 u-tips-color" @click="goNav('/pages/me/vip/index')">会员暂未开启</view>
			</view>
			<view class="text-white" style="border-radius: 29px 0px 0px 29px;padding: 7px 16px;background: #5074FF;">
				个人资料
			</view>
		</view>
		<view class="bg-white">
			<view class=" flex justify-between padding-lr-sm margin-lr padding-tb-sm radius"
				style="background: url(../../static/images/me/bg.png) 100% no-repeat;">
				<u-image src="../../static/images/me/会员图标.png" width="35px" mode="widthFix"></u-image>
				<view class="flex-sub margin-left text-lg text-bold" style="line-height: 37px;color: #604320;">
					全站海量视频无线学习
				</view>
				<view class="btn-bg">去开通</view>
			</view>
		</view>
		<view class="bg-white padding-top-sm">
			<u-grid :col="4" :border="false">
				<u-grid-item @click="goNav('/pages/me/message/index')">
					<u-image width="50rpx" height="51rpx" src="../../static/images/me/消息中心.png"></u-image>
					<view class="grid-text">消息中心</view>
				</u-grid-item>
				<u-grid-item @click="goNav('/pages/me/order/index')">
					<u-image width="48rpx" height="55rpx" src="../../static/images/me/我的订单.png"></u-image>
					<view class="grid-text">我的订单</view>
				</u-grid-item>
				<u-grid-item @click="goNav('')">
					<u-image width="48rpx" height="56rpx" src="../../static/images/me/我的课程.png"></u-image>
					<view class="grid-text">我的课程</view>
				</u-grid-item>
				<u-grid-item @click="goNav('/pages/me/invite/index')">
					<u-image width="61rpx" height="50rpx" src="../../static/images/me/我的邀请.png"></u-image>
					<view class="grid-text">我的邀请</view>
				</u-grid-item>
				<u-grid-item @click="goNav('/pages/me/integral/index')">
					<u-image width="50rpx" height="52rpx" src="../../static/images/me/我的积分.png"></u-image>
					<view class="grid-text">我的积分</view>
				</u-grid-item>
				<u-grid-item @click="goNav('')">
					<u-image width="57rpx" height="52rpx" src="../../static/images/me/我的收藏.png"></u-image>
					<view class="grid-text">我的收藏</view>
				</u-grid-item>
				<u-grid-item @click="goNav('/pages/me/setting/index')">
					<u-image width="50rpx" height="57rpx" src="../../static/images/me/设置中心.png"></u-image>
					<view class="grid-text">设置中心</view>
				</u-grid-item>
			</u-grid>
		</view>
		<view class="margin">
			<swiper class="screen-swiper" :circular="true" :autoplay="true" interval="3000" duration="500">
				<swiper-item v-for="(item,index) in swiperList" :key="index">
					<image :src="item.url" mode="widthFix"></image>
				</swiper-item>
			</swiper>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				pic: '../../static/images/me/头像.png',
				show: true,
				swiperList: [{
					url: '../../static/images/me/小banner.png',
				}]
			}
		},
		onLoad() {

		},
		methods: {
			goNav(e) {
				uni.navigateTo({
					url: e
				})
			}
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #ededed;
	}

	.user-box {
		background-color: #fff;
	}

	.btn-bg {
		width: 64px;
		height: 28px;
		background: linear-gradient(90deg, #CDA26E 0%, #DCB78A 100%);
		border-radius: 28px;
		text-align: center;
		line-height: 28px;
		margin-top: 4px;
	}

	.grid-text {
		margin-top: 5px;
	}
</style>
