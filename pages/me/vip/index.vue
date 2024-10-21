<!-- 会员中心 -->
<template>
	<view>
		<view class="margin-top margin-lr radius padding" style="background: url(../../../static/images/me/背景@2x.png) no-repeat; height: 130px;background-size: 100%;">
			<view class="text-bold u-font-40">小慕秋</view>
			<view class="margin-top-sm" style="color: #604320;">购买会员所有视频免费看</view>
		</view>
		<view class="margin-lr padding bg-white" style="border-radius: 20px;position: relative;top: -40px;">
			<view class="u-font-16 text-bold margin-bottom">开通会员</view>
			<view class="flex justify-between margin-bottom">
				<view>
					<view class="u-font-40">199.00</view>
					<view class="text-gray">月卡·199元/月</view>
				</view>
				<view class="margin-top">
					<u-button :hair-line="false" shape="circle" size="mini" :ripple="true" class="custom-style">购买</u-button>
				</view>
			</view>
			<view class="flex justify-between margin-bottom">
				<view>
					<view class="u-font-40">399.00</view>
					<view class="text-gray">季卡·199元/月</view>
				</view>
				<view class="margin-top">
					<u-button :hair-line="false" shape="circle" size="mini" :ripple="true" class="custom-style">购买</u-button>
				</view>
			</view>
			<view class="flex justify-between margin-bottom">
				<view>
					<view class="u-font-40">999.00</view>
					<view class="text-gray">年卡·199元/月</view>
				</view>
				<view class="margin-top">
					<u-button :hair-line="false" shape="circle" size="mini" :ripple="true" class="custom-style">购买</u-button>
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
	.custom-style {
		background: linear-gradient(90deg, #DBC084 0%, #E9D4A6 100%);
		padding: 0px 16px;
		border: 0px;
		color: #604320;
	}
</style>
