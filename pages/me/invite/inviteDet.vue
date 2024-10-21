<template>
	<view>
		<view class="padding margin radius bg-white" style="">
			<view class="text-19">当前收益</view>
			<view class="flex justify-between margin-top">
				<view class="text-bold">¥<text style="font-size: 34px;">120</text></view>
				<view class="" style="position: relative;overflow: hidden;width: 90px;">
					<view style="position: absolute;bottom:0;">
						<!-- <view class="flex"> -->
							<button class="cu-btn round">立即提现</button>
						<!-- </view> -->
					</view>
				</view>
			</view>
		</view>
		<view class="margin padding bg-white radius">
			<view class="u-font-16 text-bold margin-bottom">余额明细</view>
			<view class="flex justify-between" style="line-height: 30px;">
				<view class="flex">
					<u-image src="../../../static/images/me/图层 5@2x.png" width="30px" mode="widthFix"></u-image>
					<text class="margin-left-sm">按时睡觉</text>
				</view>
				<view>成功注册</view>
				<view>
					<text class="margin-left text-red">赚29.7</text>
				</view>
			</view>
			<view class="flex justify-between" style="line-height: 30px;">
				<view class="flex">
					<u-image src="../../../static/images/me/图层 6@2x.png" width="30px" mode="widthFix"></u-image>
					<text class="margin-left-sm">按时睡觉</text>
				</view>
				<view>购买课程</view>
				<view>
					<text class="margin-left text-red">赚29.7</text>
				</view>
			</view>
			<view class="flex justify-between" style="line-height: 30px;">
				<view class="flex">
					<u-image src="../../../static/images/me/图层 7@2x.png" width="30px" mode="widthFix"></u-image>
					<text class="margin-left-sm">按时睡觉</text>
				</view>
				<view>注册会员</view>
				<view>
					<text class="margin-left text-red">赚29.7</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		}
	}
</script>

<style>
	.cu-btn {
		background: #E5EBFF;
		color: #5074FF;
		font-weight: bold;
		font-size: 14px;
	}
</style>
