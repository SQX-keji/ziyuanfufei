<!-- 我的积分 -->
<template>
	<view class="">
		<view class="padding margin radius" style="background: url(../../../static/images/me/背景.png) 100% no-repeat;">
			<view class="text-19">当前积分</view>
			<view class="flex justify-between margin-top">
				<view class="text-bold" style="font-size: 34px;">1</view>
				<view class="" style="position: relative;overflow: hidden;width: 90px;">
					<view style="position: absolute;bottom:0;">
						<view class="flex">
							<u-image src="../../../static/images/me/积分明细.png" width="43rpx" height="37rpx"></u-image>
							<view class="margin-left-sm">积分明细</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<u-gap height="30" bg-color="#F7F7F7"></u-gap>
		<view class="margin">
			<view class="flex justify-between u-border-bottom padding-tb">
				<view class="u-font-16 text-bold">注册赠送</view>
				<view class="flex justify-between" style="width: 60px;border: 1px solid #FFA800;background: rgba(255, 247, 226, 0.5);border-radius: 18px;">
					<u-icon name="../../../static/images/me/金币.png" width="18px" height="18px"></u-icon>
					<view class="margin-right-sm" style="line-height: 18px;">+2</view>
				</view>
			</view>
			<view class="flex justify-between u-border-bottom padding-tb">
				<view class="u-font-16 text-bold">邀请好友</view>
				<view class="flex justify-between" style="width: 60px;border: 1px solid #FFA800;background: rgba(255, 247, 226, 0.5);border-radius: 18px;">
					<u-icon name="../../../static/images/me/金币.png" width="18px" height="18px"></u-icon>
					<view class="margin-right-sm" style="line-height: 18px;">+12</view>
				</view>
			</view>
			<view class="flex justify-between u-border-bottom padding-tb">
				<view class="u-font-16 text-bold">邀请好友</view>
				<view class="flex justify-between" style="width: 60px;border: 1px solid #FFA800;background: rgba(255, 247, 226, 0.5);border-radius: 18px;">
					<u-icon name="../../../static/images/me/金币.png" width="18px" height="18px"></u-icon>
					<view class="margin-right-sm" style="line-height: 18px;">+12</view>
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
	page {
		background-color: #FFFFFF;
	}
</style>
