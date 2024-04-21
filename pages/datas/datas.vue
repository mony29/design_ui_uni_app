<template>
	<view>
		<uni-section title="显示图标或图片" type="line">
					<uni-list>
						<uni-list-item :show-extra-icon="true" showArrow :extra-icon="extraIcon" title="列表左侧带扩展图标" />
						<uni-list-item title="列表左侧带略缩图" note="列表描述信息" showArrow
							thumb="https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/unicloudlogo.png"
							thumb-size="sm" rightText="小图" />
		
						<uni-list-item title="列表左侧带略缩图" note="列表描述信息" showArrow
							thumb="https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/unicloudlogo.png"
							thumb-size="base" rightText="默认" />
						<uni-list-item title="列表左侧带略缩图" note="列表描述信息" showArrow
							thumb="https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/unicloudlogo.png"
							thumb-size="lg" rightText="大图" />
					</uni-list>
				</uni-section>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				gutter: 0,
				nvueWidth: 730
			}
		}
	}
</script>

<style>
	.example-body {
		/* #ifndef APP-NVUE */
		display: block;
		/* #endif */
		padding: 5rpx 10rpx 0;
		overflow: hidden;
	}
</style>
