<!-- 我的邀请 -->
<template>
	<view>
		<!-- <u-image src="../../../static/images/me/矩形 11@2x.png" width="100%" mode="widthFix"></u-image> -->
		<img src="../../../static/images/me/矩形 11@2x.png" alt="" width="100%" mode="widthFix">
		<view class="padding">
			<view class="text-center padding-top yaoqing">
				<view class="margin-top-xl padding-top-sm text-xxl text-red text-bold">U4359131</view>
				<u-button class="margin-top-sm customStyle" :hair-line="false" shape="circle" size="mini"
					:ripple="true">复制邀请码</u-button>
			</view>
		</view>
		<view class="margin padding bg-white radius">
			<view class="flex justify-between" style="line-height: 40px;">
				<view class="flex">
					<u-image src="../../../static/images/me/图层 5@2x.png" width="40px" mode="widthFix"></u-image>
					<text class="margin-left-sm">按时睡觉</text>
				</view>
				<view>
					<text>获得</text>
					<text class="margin-left text-red">29.7 元现金</text>
				</view>
			</view>
			<view class="flex justify-between" style="line-height: 40px;">
				<view class="flex">
					<u-image src="../../../static/images/me/图层 6@2x.png" width="40px" mode="widthFix"></u-image>
					<text class="margin-left-sm">按时睡觉</text>
				</view>
				<view>
					<text>获得</text>
					<text class="margin-left text-red">29.7 元现金</text>
				</view>
			</view>
			<view class="flex justify-between" style="line-height: 40px;">
				<view class="flex">
					<u-image src="../../../static/images/me/图层 7@2x.png" width="40px" mode="widthFix"></u-image>
					<text class="margin-left-sm">按时睡觉</text>
				</view>
				<view>
					<text>获得</text>
					<text class="margin-left text-red">29.7 元现金</text>
				</view>
			</view>
		</view>
		<view class="padding">
			<view class="text-center padding-top flex justify-center flex-direction zhanji" style="">
				<view class="flex justify-around margin-top-sm" @click="goNav('/pages/me/invite/inviteDet')">
					<view>
						<view class="margin-bottom-sm">已邀请</view>
						<view class="text-red"><text class="text-bold u-font-18">1</text>人</view>
					</view>
					<view>
						<view class="margin-bottom-sm">累计收益</view>
						<view class="text-red"><text class="text-bold u-font-18">1</text>元</view>
					</view>
					<view>
						<view class="margin-bottom-sm">已提现</view>
						<view class="text-red">¥<text class="text-bold u-font-18">0</text></view>
					</view>
				</view>
			</view>
		</view>
		<view class="padding">
			<view class="padding-top jiqiao" style="">
				<view class="padding-top-xl padding-lr padding-bottom" style="line-height: 24px;">
					<view class="flex">
						<text class="cuIcon-title text-yellow"></text>
						<view>使用该邀请码的用户将获得</view>
					</view>
					<view class="flex">
						<text class="cuIcon-title text-yellow"></text>
						<view>当用户使用您的邀请码支付并完成订单的时候，您也将获得10元奖励</view>
					</view>
					<view class="flex">
						<text class="cuIcon-title text-yellow"></text>
						<view>使用您的邀请码完成支付的用户将自动成为您的下级，TA的每一笔已支付订单您将享有1%的抽成</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			
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

<style>
	page {
		background: #E0EFFF;
	}

	img {
		display: block;
	}

	.customStyle {
		background: #FFE0E0;
		border: 0;
		color: #FE1E23;
		font-size: 12px;
		font-weight: 500;
		padding: 15px 20px;
	}

	.yaoqing {
		width: 100%;
		height: 136px;
		background: url('../../../static/images/me/分享邀请码@2x.png');
		background-size: 100%;
		background-repeat: no-repeat;
	}

	.zhanji {
		width: 100%;
		height: 119px;
		background: url('../../../static/images/me/我的邀请战绩@2x.png');
		background-size: 100%;
		background-repeat: no-repeat;
	}

	.jiqiao {
		width: 100%;
		height: auto;
		background: url('../../../static/images/me/邀请小技巧@2x.png');
		background-size: 100%;
		background-repeat: no-repeat;
	}
</style>
