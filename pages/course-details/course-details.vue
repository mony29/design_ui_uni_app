<template>
	<view v-if="courseData">
		<h1>Course Details name : {{ courseData.name }}</h1>
		<p>Course ID: {{ courseData.price }}</p>
	</view>
	<view v-else>
		Loading data ...
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// courseData: null
			}
		},
		onLoad() {
			// this.courseId = uni.getPageData().id;
		},
		methods: {
			fetchCourseDetails(courseId){
				
			}
		},
		mounted() {
			const courseId = this.$route.query.id; // Access ID from query parameters
			console.log(`Course ID: ${courseId}`);
			this.fetchCourseDetails(courseId)
		}
	}
</script>

<style>

</style>