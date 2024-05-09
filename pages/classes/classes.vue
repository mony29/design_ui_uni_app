<template>
	<view>
		<uni-section title="显示图标或图片" type="line">
			<uni-list>
				<uni-list-item title="列表左侧带略缩图" showArrow
					thumb="https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/unicloudlogo.png" thumb-size="base" />
				<uni-list-item title="列表左侧带略缩图" showArrow
					thumb="https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/unicloudlogo.png" thumb-size="base" />
			</uni-list>
		</uni-section>

		<uni-section title="课程列表" type="line">
			<uni-list>
				<uni-list-item v-for="course in courseList" :key="course.id" :title="course.name"
					:note="course.price" :thumb="course.image" showArrow thumb-size="base" clickable @click="onCourseClick(course)" />
			</uni-list>
		</uni-section>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				gutter: 0,
				nvueWidth: 730,
				courseList: [{
						id: '1',
						name: 'Java程序设计',
						image: "../../static/book1.png",
						price: 29
					},
					{
						id: '2',
						name: '数据结果',
						image: "../../static/book2.jpg",
						price: 8
					},
					{
						id: '3',
						name: '机器学习',
						image: "../../static/book1.png",
						price: 29
					}
				]
			}
		},
		
		methods: {
			onCourseClick(course){
				console.log("Clicked!")
				console.log(`Course ID: ${course.id}`);
				uni.navigateTo({
					url: `/pages/course-details/course-details?id=${course.id}`
					// url: `/pages/course-details/course-details`,
					// data: course
				})
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