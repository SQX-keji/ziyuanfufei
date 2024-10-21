<template>
	<view class="">
		<view class="padding-lr padding-top-sm bg-white" @click.stop="goSearch">
			<u-search  placeholder="UI进阶公开课" v-model="keyword" shape="square" :show-action="false" :animation="true"></u-search>
		</view>
		<view class="wrap">
			<view class="u-tabs-box">
				<u-tabs-swiper active-color="#5074FF" ref="tabs" :list="tabList" :current="current" @change="change"
					:is-scroll="false" swiperWidth="750"></u-tabs-swiper>
			</view>
			<swiper class="swiper-box" :current="swiperCurrent" @transition="transition"
				@animationfinish="animationfinish">
				<!-- 推荐 -->
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;">
						<view>
							<view class="padding-tb-sm bg-white">
								<u-swiper bg-color='#ffffff' :list="swiperList" :effect3d="true"></u-swiper>
							</view>
							<u-grid :col="4" :border="false">
								<u-grid-item>
									<u-image width="90rpx" height="90rpx" src="@/static/images/index/热门课程@2x.png">
									</u-image>
									<view class="grid-text">热门课程</view>
								</u-grid-item>
								<u-grid-item>
									<u-image width="90rpx" height="90rpx" src="@/static/images/index/名师课堂@2x.png">
									</u-image>
									<view class="grid-text">名师课堂</view>
								</u-grid-item>
								<u-grid-item>
									<u-image width="90rpx" height="90rpx" src="@/static/images/index/特价优惠@2x.png">
									</u-image>
									<view class="grid-text">价格优惠</view>
								</u-grid-item>
								<u-grid-item>
									<u-image width="90rpx" height="90rpx" src="@/static/images/index/免费体验@2x.png">
									</u-image>
									<view class="grid-text">免费体检</view>
								</u-grid-item>
							</u-grid>
							<view class="flex margin-tb-sm margin-lr bg-white radius padding-lr-sm">
								<u-image width="54px" height="12px" src="../../static/images/index/最新公告@2x.png" class="margin-top-sm"></u-image>
								<u-notice-bar :volume-icon="false" class="flex-sub" type="none" mode="vertical" :list="noticeList"></u-notice-bar>
							</view>
							<view class="padding-lr">
								<view class="flex justify-between margin-bottom-sm">
									<view class="text-black text-xl text-bold">推荐课程</view>
									<view class="text-gray">
										更多
										<u-icon name="arrow-right"></u-icon>
									</view>
								</view>
								<view class="flex justify-between flex-wrap">
									<view v-for="(item, index) in courseList" :key="index" @click="goCourse(item.id)" class="bg-white padding-sm radius margin-bottom-sm" style="width: 48%;">
										<u-image width="100%" mode="widthFix" :src="item.image"></u-image>
										<view class="text-bold text-black margin-top-sm u-line-1 text-xl">{{item.title}}</view>
										<u-tag class="margin-top-sm" :text="item.tag" mode="light" size="mini" bg-color="#FFEEE5" color="#FF5A00" border-color="#FF5A00" />
										<view class="flex justify-between margin-top-sm">
											<view class="text-red text-bold text-lg">¥{{item.price}}</view>
											<view class="text-gray">{{item.munber}}人已学</view>
										</view>
									</view>
								</view>
							</view>
							
						</view>
					</scroll-view>
				</swiper-item>
				<!-- 前端 -->
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">
						<view class="padding-lr">
							<view class="flex justify-between flex-wrap">
								<view v-for="(item, index) in courseList" :key="index" @click="goCourse(item.id)" class="bg-white padding-sm radius margin-bottom-sm" style="width: 48%;">
									<u-image width="100%" mode="widthFix" :src="item.image"></u-image>
									<view class="text-bold text-black margin-top-sm u-line-1 text-xl">{{item.title}}</view>
									<u-tag class="margin-top-sm" :text="item.tag" mode="light" size="mini" bg-color="#FFEEE5" color="#FF5A00" border-color="#FF5A00" />
									<view class="flex justify-between margin-top-sm">
										<view class="text-red text-bold text-lg">¥{{item.price}}</view>
										<view class="text-gray">{{item.munber}}人已学</view>
									</view>
								</view>
							</view>
							<view class="flex justify-between flex-wrap">
								<view v-for="(item, index) in courseList" :key="index" @click="goCourse(item.id)" class="bg-white padding-sm radius margin-bottom-sm" style="width: 48%;">
									<u-image width="100%" mode="widthFix" :src="item.image"></u-image>
									<view class="text-bold text-black margin-top-sm u-line-1 text-xl">{{item.title}}</view>
									<u-tag class="margin-top-sm" :text="item.tag" mode="light" size="mini" bg-color="#FFEEE5" color="#FF5A00" border-color="#FF5A00" />
									<view class="flex justify-between margin-top-sm">
										<view class="text-red text-bold text-lg">¥{{item.price}}</view>
										<view class="text-gray">{{item.munber}}人已学</view>
									</view>
								</view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">

					</scroll-view>
				</swiper-item>
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">

					</scroll-view>
				</swiper-item>
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">

					</scroll-view>
				</swiper-item>
				<swiper-item class="swiper-item">
					<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="reachBottom">

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
				keyword: '',
				tabList: [{
						name: '推荐'
					},
					{
						name: '前端'
					},
					{
						name: 'UI设计'
					},
					{
						name: '后端'
					},
					{
						name: '数据库'
					},
					{
						name: '云计算'
					}
				],
				swiperList: [{
						image: 'https://cdn.uviewui.com/uview/swiper/1.jpg',
						title: '昨夜星辰昨夜风，画楼西畔桂堂东'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
						title: '身无彩凤双飞翼，心有灵犀一点通'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
						title: '谁念西风独自凉，萧萧黄叶闭疏窗，沉思往事立残阳'
					}
				],
				noticeList: ['UI设计进阶第六期预约即将截止!'],
				courseList: [
					{
						id: '1',
						image: '../../static/images/index/图层 9@2x.png',
						title: '偏轴式排版进阶版拆解',
						tag: '平面UI设计',
						price: '129',
						munber: '1330'
					},
					{
						id: '2',
						image: '../../static/images/index/图层 10@2x.png',
						title: '扁平式插画风格',
						tag: '插画设计',
						price: '76',
						munber: '1230'
					},
					{
						id: '3',
						image: '../../static/images/index/图层 9@2x.png',
						title: '偏轴式排版进阶版拆解',
						tag: '平面UI设计',
						price: '129',
						munber: '1330'
					},
					{
						id: '4',
						image: '../../static/images/index/图层 10@2x.png',
						title: '扁平式插画风格',
						tag: '插画设计',
						price: '76',
						munber: '1230'
					}
				],
				current: 0,
				swiperCurrent: 0,
				tabsHeight: 0,
				dx: 0,
				loadStatus: ['loadmore', 'loadmore', 'loadmore', 'loadmore'],
				
			};
		},
		onLoad() {
			this.getOrderList(0);
		},
		methods: {
			goCourse(e) {
				uni.navigateTo({
					url: '/pages/index/course/courseDet?id=' + e
				});
			},
			goSearch() {
				uni.navigateTo({
					url: '/pages/index/search/index'
				});
			},
			
			
			
			reachBottom() {
				// 此tab为空数据
				if (this.current != 2) {
					this.loadStatus.splice(this.current, 1, "loading")
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
	.wrap {
		display: flex;
		flex-direction: column;
		height: calc(100vh - var(--window-top));
		width: 100%;
	}

	.swiper-box {
		flex: 1;
	}

	// .swiper-item {
	// 	height: 100%;
	// }
</style>
