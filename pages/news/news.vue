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

	<view class="title">
		<text>Category</text>
	</view>
	
	<view class="category-container">
		<view class="category-row">
			<view class="category-item">
				<view class="category-image">
					<image src="../../static/ronaldo.jpg"></image>
				</view>
				<view class="category-text-wrapper">
					<text class="category-title">Ronaldo news</text>
					<text class="category-description">\nThis is a description for category 3.</text>
				</view>
			</view>
		</view>
		<view class="category-row">
			<view class="category-item">
				<view class="category-image">
					<image src="../../static/ronaldo.jpg"></image>
				</view>
				<view class="category-text-wrapper">
					<text class="category-title">Ronaldo news</text>
					<text class="category-description">\nThis is a description for category 3. is is a description for category 3.</text>
				</view>
			</view>
		</view>
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
				duration: 500
			}
		},
		onLoad() {

		},
		methods: {

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

	.title{
		margin-top: 10px;
		color: white;
		padding: 5px;
		display: inline;
		background-color: #F76260;
		font-size: 20px;
		margin-left: 10px;
	}

	.category-container {
		display: flex;
		flex-direction: column;
		/* background-color: #D6D6D6; */
		/* margin-top: 10px; */
		/* Arrange rows vertically */
	}

	.category-row {
		margin: 10px;
		border-radius: 8px;
		/* display: flex; */
		/* Arrange items in a row */
		/* flex-wrap: wrap; */
		/* Allow items to wrap to multiple lines if needed */
		/* margin-top: 20rpx; */
		/* Add some margin between rows */
	}

	.category-item {
		display: flex;
		background-color: #D6D6D6;
		border-radius: 8px;
		/* Arrange image and text side-by-side */
	}

	.category-image {
		width: 40%;
		padding: 10px;
		/* Image takes half the width of the item */
		/* height: 150rpx; */
		/* Set a fixed height for the image */
		/* object-fit: cover; */
		/* Resize image to fit container */
	}
	
	.category-image image{
		border-radius: 8px;
		width: 100%;
		height: 180rpx;
		object-fit: cover;
	}

	.category-text-wrapper {
		width: 60%;
		/* Text wrapper takes the remaining half width */
		padding: 10rpx;
		/* background-color: #F76260; */
		margin-top: 10px;
	}
	.category-text-wrapper .category-title{
		margin-top: 10px;
		font-weight: 600;
		font-size: 16px;
	}
	.category-text-wrapper .category-description{
		font-weight: 400;
		font-size: 14px;
	}
</style>