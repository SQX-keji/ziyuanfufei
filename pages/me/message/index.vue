<!-- 消息中心 -->
<template>
	<view>
		<u-navbar :title-bold="true" title="消息中心">
			<view class="slot-wrap margin-right" slot="right">全部已读</view>
		</u-navbar>
		<view class="flex margin-lr padding-tb-sm u-border-bottom">
			<u-image src="../../../static/images/me/系统消息.png" width="82rpx" mode="widthFix"></u-image>
			<view class="flex-sub margin-left">
				<view class="flex justify-between">
					<view class="text-bold text-lg">系统消息</view>
					<view class="text-gray">12/18 09:46</view>
				</view>
				<view class="text-gray">感谢您注册成为本站会员</view>
			</view>
		</view>
		<view class="flex margin-lr padding-tb-sm u-border-bottom">
			<u-image src="../../../static/images/me/积分消息.png" width="82rpx" mode="widthFix"></u-image>
			<view class="flex-sub margin-left">
				<view class="flex justify-between">
					<view class="text-bold text-lg">积分消息</view>
					<view class="text-gray">12/18 09:46</view>
				</view>
				<view class="text-gray">注册赠送一枚积分</view>
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
		background-color: white;
	}
</style>
