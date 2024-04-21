<template>
	<view class="uni-margin-wrap">
		<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
			:duration="duration">
			<swiper-item>
				<view class="swiper-item uni-bg-red">
					<image src="../../static/hazard.jpg" class="swiper-item-image" mode=""></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item uni-bg-red">
					<image src="../../static/messi.jpg" class="swiper-item-image" mode=""></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item uni-bg-red">
					<image src="../../static/ronaldo.jpg" class="swiper-item-image" mode=""></image>
				</view>
			</swiper-item>
		</swiper>
	</view>

	<view>
		<uni-section title="自定义列数" type="line" padding>
			<uni-grid :column="3" :highlight="true" @change="change">
				<uni-grid-item v-for="item in gridItems" :key="item.id">
					<view class="grid-item-box" style="background-color: #fff;">
						<uni-icons :type="item.iconType" :size="40" color="#ffffff"
							style="background-color: #f43530; padding: 12rpx; margin-bottom: 8rpx; border-radius: 50%;" />
						<navigator :url="item.navigationUrl">
							<text class="text">{{ item.text}}</text>
						</navigator>
					</view>
				</uni-grid-item>
			</uni-grid>
		</uni-section>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				background: ['color1', 'color2', 'color3'],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				gridItems: [{
						id: 1,
						iconType: 'person',
						text: '个人信息',
						navigationUrl: '/pages/user-info/user-info',
						backgroundColor: '#e0e0e0',
					},
					{
						id: 2,
						iconType: 'chat',
						text: '编辑页面',
						navigationUrl: '/pages/user-edit/user-edit',
						backgroundColor: '#f0f0f0',
					},
					{
						id: 3,
						iconType: 'bars',
						text: '其他页面',
						navigationUrl: '',
						backgroundColor: '#f0f0f0',
					},
					{
						id: 4,
						iconType: 'bars',
						text: '其他页面',
						navigationUrl: '',
					},
					{
						id: 5,
						iconType: 'bars',
						text: '其他页面',
						navigationUrl: '',
					},
					{
						id: 6,
						iconType: 'bars',
						text: '其他页面',
						navigationUrl: '',
					}
				],
			}
		},
		onLoad() {

		},
		methods: {
			getNavigationUrl(index) {
				// Access the corresponding URL from navigationUrls based on the item index
				return this.navigationUrls[index] || ''; // Return an empty string if index is out of bounds
			},
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}

	.uni-margin-wrap {
		width: 690rpx;
		width: 100%;
	}

	.swiper {
		height: 360rpx;
	}

	.swiper-item {
		display: block;
		height: 360rpx;
		line-height: 360rpx;
		text-align: center;
		color: #FFF;
		background-color: inherit;
		/* Inherit from parent */
	}

	.swiper-item image.swiper-item-image {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.swiper-item.uni-bg-red {
		background-color: #F76260;
	}

	.swiper-item.uni-bg-green {
		background-color: #09BB07;
	}
/* 
	.btn-user-info {
		margin-top: 20px;
		margin-left: 20px;
		width: 100px;
		text-align: center;
		background-color: #F76260;
		padding: 8px 5px;
		border-radius: 8px;
	}

	.btn-edit {
		margin-top: 20px;
		margin-left: 20px;
		width: 100px;
		text-align: center;
		background-color: #09BB07;
		padding: 8px 5px;
		border-radius: 8px;
	} */

	.uni-flex {
		display: flex;
	}

	.flex-item {
		/* width: 33.3%; */
		/* height: 200rpx; */
		text-align: center;
		/* line-height: 200rpx; */
		background-color: #F76260;
	}

	.item {
		display: flex;
	}

	.item-item {
		/* width: 40%; */
		background-color: #8f8f94;
	}

	.grid-item-box {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		/* padding: 15px 0; */
	}

	.text {
		font-size: 14px;
		margin-top: 5px;
	}
</style>